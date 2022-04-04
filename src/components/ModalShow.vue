<template>
  <section class="modal-new d-none" id="modal-details">
    <article class="row justify-content-center mt-6">
      <div class="col-md-6">
        <div class="card">
          <div class="card-body p-5 pt-4 pb-4">
            <div class="text-end">
              <a href="" class="exit" id="close-modal-details">X</a>
            </div>
            <section class="row align-items-center">
              <article class="col-md-3">
                <img
                  src="/assets/img/inspired.png"
                  class="rounded-circle"
                  width="137px"
                  height="137px"
                  alt="..."
                />
              </article>
              <div class="col-md-8">
                <div class="contact-modal-name">{{ details.name }}</div>
                <span class="contact-modal-email">
                  {{ details.email }}
                  <i
                    class="fa fa-envelope icon-edited"
                    style="padding-left: 0.1em; padding-right:0px; font-size:25px"
                  ></i>
                </span>
              </div>
            </section>
            <section class="row pb-4">
              <div class="col-md-12">
                <div class="modal-details-font">
                  <span class=""><i class="fa fa-house icon-edited"></i> </span
                  >{{ details.company.name }}
                </div>
              </div>
              <div class="col-md-12">
                <div class="modal-details-font">
                  <span class=""><i class="fa fa-phone icon-edited"></i> </span
                  >{{ details.phone }}
                </div>
              </div>
              <div class="col-md-12">
                <div class="modal-details-font">
                  <span class=""><i class="fa fa-map icon-edited"></i> </span
                  >{{ details.address.street }}, {{ details.address.city }}
                </div>
              </div>
              <div class="col-md-12">
                <div class="modal-details-font">
                  <span class=""><i class="fa fa-image icon-edited"></i> </span
                  >{{ details.address.zipCode }}
                </div>
              </div>
              <div class="col-md-8">
                <div class="font-size-5">
                  <span class=""
                    ><i class="fa fa-bookmark icon-edited"></i> </span
                  >{{ details.company.type }}
                </div>
              </div>
              <div
                class="
                  col-md-4
                  text-right
                  d-flex
                  align-items-end
                  justify-content-end
                "
              >
                <button class="btn p-0">
                  <i class="fa fa-trash-can icon-delete"></i>
                </button>
              </div>
            </section>
          </div>
        </div>
      </div>
    </article>
  </section>
</template>


<script>
export default {
  props: {
    details: {
      type: Object,
      //   required: true
    },
  },
};
</script>