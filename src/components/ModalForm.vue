<template>
  <section class="modal-new d-none" id="modal-contact">
    <article class="row justify-content-center mt-6">
      <div class="col-md-6">
        <div class="card">
          <div class="card-body p-5 pt-4 pb-4">
            <div class="text-end">
              <a href="" class="exit" id="close-modal-contact">X</a>
            </div>
            <h5 class="card-title text-green fw-bold title-addcontact">
              + Novo Contacto
            </h5>
            <form action="" id="modal-contact-form">
              <div class="row">
                <div class="col-md-6 form-group">
                  <label for="" class="pt-4">Nome</label>
                  <input type="text" class="form-control" />
                </div>
                <div class="col-md-6 form-group">
                  <label for="" class="pt-4">Email</label>
                  <input type="text" class="form-control" />
                </div>
                <div class="col-md-6 form-group">
                  <label for="" class="pt-4">Telefone</label>
                  <input type="text" class="form-control" />
                </div>
                <div class="col-md-6 form-group">
                  <label for="" class="pt-4">Website</label>
                  <input type="text" class="form-control" />
                </div>
                <div class="col-md-6 form-group">
                  <label for="" class="pt-4">Nome da Empresa</label>
                  <input type="text" class="form-control" />
                </div>
                <div class="col-md-6 form-group">
                  <label for="" class="pt-4">Categorias</label>
                  <select name="categorias[]" id="" class="form-control">
                    <option value="" disabled selected></option>
                    <option value="Teach">Teach</option>
                    <option value="Solutions">Solutions</option>
                  </select>
                </div>
                <div class="col-md-6 form-group">
                  <label for="" class="pt-4">Rua</label>
                  <input type="text" class="form-control" />
                </div>
                <div class="col-md-6 form-group">
                  <label for="" class="pt-4">Cidade</label>
                  <input type="text" class="form-control" />
                </div>
                <div class="col-md-6 form-group">
                  <label for="" class="pt-4">Codigo Postal</label>
                  <input type="text" class="form-control" />
                </div>
                <div class="col-md-12 form-group text-end">
                  <button class="btn btn-success mt-4 w-50">
                    Gravar Contacto
                  </button>
                </div>
              </div>
            </form>
          </div>
        </div>
      </div>
    </article>
  </section>
</template>


