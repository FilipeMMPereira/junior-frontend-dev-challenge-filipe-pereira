<template>
  <div>
    <Navbar />
    <ModalForm />
    <ModalShow v-bind:details="details"/>
    <main>
      <Background />
      
      <!-- Container -->
      <section class="container">
        <section class="row pt-5">
          <!-- Left -->
          <article class="col-md-4">
            <!-- Adicionar Contacto -->
            <section class="card add-contact text-center mb-5">
              <div class="card-body">
                <div
                  class="
                    border-contact
                    d-flex
                    justify-content-center
                    align-items-center
                    mt-3
                  "
                >
                  <span>+</span>
                </div>
                <h6 class="card-subtitle mb-2 mt-4 text-muted text-white">
                  Adicionar Contacto
                </h6>

                <button
                  type="button"
                  class="btn btn-light mt-3 mb-2 add-contact-button"
                  id="open-modal-contact"
                >
                  Novo Contacto
                </button>
              </div>
              
            </section>
            <!-- End Adicionar Contacto -->
            <!-- Banner -->
            <section class="card mt-2 mb-5">
              <div class="card-body p-5 pt-2 pb-0">
                <!-- <h5 class="card-title">Card title</h5> -->

                <h3 class="card-subtitle mb-2 mt-4 text-body">
                  Cuidamos do seu <br />
                  <span class="text-green"> Negocio.</span>
                </h3>

                <p class="pt-3">
                  Uma plataforma especializada na prospecção de novos clientes
                  para o seu negócio.
                </p>
              </div>
              <div class="elipse-people">
                <img src="/assets/img/inspired.png" alt="" class="img-fluid" />
              </div>
            </section>
            <!-- End Banner -->
          </article>
          <!-- End Left -->

          <!-- Rigth -->
          <article class="col-md-8">
            <section class="card mb-5">
              <div class="card-body p-5 pt-2 pb-4">
                <div class="row align-items-end mt-3">
                  <div class="col-md-2">
                    <h1 class="text-green font-size-4 fw-bold">45</h1>
                  </div>
                  <div class="col-md-10">
                    <h1>
                      Contactos <span class="text-green">Adicionados</span>
                    </h1>
                    <p>
                      Uma plataforma especializada na prospecção de novos
                      clientes para o seu negócio.
                    </p>
                  </div>
                </div>
                <!-- Search -->
                <form action="" class="pt-4">
                  <div class="row align-items-center">
                    <div class="col-md-4 form-group">
                      <label for="">Nome</label>
                      <input type="text" class="form-control" />
                    </div>
                    <div class="col-md-4 form-group">
                      <label for="">Empresa</label>
                      <input type="text" class="form-control" />
                    </div>
                    <div class="col-md-4 form-group d-flex justify-content-end">
                      <button class="btn">
                        <img src="/assets/img/Vector.png" alt="" />
                      </button>
                    </div>
                  </div>
                </form>
                <!-- End Search -->
              </div>
            </section>
            <!-- Contact List -->
            <section class="row">
              <div
                class="col-md-4 pb-3"
                v-for="(contactInfo, index) in contacts"
                v-bind:key="index" 
              >
                <div class="card">
                  <div class="card-body p-3 pt-2 pb-2">
                    <section class="row mt-3">
                      <article class="col-md-3">
                        <img
                          src="/assets/img/inspired.png"
                          class="rounded-circle"
                          width="55px"
                          height="55px"
                          alt="..."
                        />
                      </article>
                      <article class="col-md-9">
                        <div class="contact-name">{{ contactInfo.name }}</div>
                        <span class="contact-email">{{
                          contactInfo.email
                        }}</span>
                      </article>
                    </section>
                    <section class="pt-2" style="margin-left: 1.5em">
                      <div class="font-size-1">
                        <span class="fw-bold">Empresa:</span>
                        {{ contactInfo.company.name }}
                      </div>
                      <div class="font-size-1">
                        <span class="fw-bold">website:</span>
                        {{ contactInfo.website }}
                      </div>
                      <div class="font-size-1">
                        <span class="fw-bold">Codigo Postal:</span>
                        {{ contactInfo.address.zipCode }}
                      </div>
                    </section>
                    <section
                      class="row align-items-center pb-2"
                      style="margin-left: 0.8em"
                    >
                      <article class="col-md-10">
                        <div class="phone-number">
                          <span>+258 </span> {{ contactInfo.phone }}
                        </div>
                      </article>
                      <article class="col-md-2">
                        <button class="btn p-0" style="margin-top: 0.8em" v-on:click.prevent="modalShow(contactInfo)">
                          <img src="/assets/img/minimize2.png" alt="" />
                        </button>
                      </article>
                    </section>
                  </div>
                </div>
              </div>
            </section>
          </article>
        </section>
      </section>
    </main>
  </div>
</template>
<script>
import Navbar from "./components/Navbar.vue";
import Background from "./components/Background.vue";
import ModalForm from "./components/ModalForm.vue";
import ModalShow from "./components/ModalShow.vue";
import axios from "axios";

export default {
  data: function () {
    return {
      contacts: [],
      details:{
        name: "",
        email: "",
        phone: "",
        company: {
          name: "",
          catchPhrase: "",
          bs: "",
        },
        address: {
          street: "",
          suite: "",
          city: "",
          zipCode: "",
        },
        website: "",
        company: {
          name: "",
          catchPhrase: "",
          bs: "",
        },
      },
    };
  },
  components: {
    Navbar,
    Background,
    ModalForm,
    ModalShow
  },
  mounted: function () {
    this.index();

  },
  methods: {
    index() {
      // axios.defaults.headers.common['Access-Control-Allow-Origin'] = '*';

      axios
        .get(
          "https://34100289-review-master-8dyme2.preview.eks.technoplus.link/api/v1/contacts"
        )
        .then((doc) => {
          console.log(doc.data);
          this.contacts = doc.data;
        })
        .catch((error) => {
          console.log(error);
        });
    },
    modalShow(contactInfo){
      this.details=contactInfo;
      // console.log(contactInfo)
      document.getElementById('modal-details').classList.remove('d-none');
    }
  },
};
</script>