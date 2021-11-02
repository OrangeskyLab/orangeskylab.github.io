<template>
  <section class="overview-block-ptb grey-bg iq-specialities">
    <div class="container">
      <div class="row">
        <div class="col-sm-12">
          <div class="heading-title">
            <h3 class="title iq-tw-7">
              You can customize and integrate the platform by your needs
            </h3>
            <!-- <p>
              Sofbox is popular for the below specialities that can make your
              website look beautiful
            </p> -->
          </div>
        </div>
      </div>
      <div class="row">
        <div
          v-for="(item, index) of list"
          :key="index"
          class="col-sm-12 col-lg-4 col-md-6 iq-mb-30"
        >
          <CardStyle6>
            <i slot="cardMedia" aria-hidden="true" :class="item.icon"></i>
            <div slot="cardBody">
              <h5 class="iq-tw-7 iq-pt-20 iq-pb-10">
                {{ item.title }}
              </h5>
              <p>{{ item.description }}</p>
            </div>
          </CardStyle6>
        </div>
      </div>
      <div class="row justify-content-center">

          <a href="javascript:void(0)" class="button iq-mt-15">Request Demo</a>

      </div>
    </div>
  </section>
</template>
<script>
export default {
  name: "Specialites",
  data() {
    return {
      list: [
        {
          icon: "ion-ios-monitor-outline",
          title: "Multi-accounts and sub-account functionalities",
          description:
            "We allows you to set-up your master entity and multiple funds, managed accounts, sub-accounts for different team members, clients, or investors.",
        },
        {
          icon: "ion-ios-settings",
          title: "Configurable and on-demand views",
          description:
            "Our core strengths is flexibility. Customize your dashboard views with widgets and indicators and track activity unique to your business needs. ",
        },
        {
          icon: "ion-social-googleplus-outline",
          title: "Multi wallet tracking",
          description:
            "You can quickly view your balances across all of your wallets.",
        },
        {
          icon: "ion-ios-heart-outline",
          title: "Trade extractions including fees and funding",
          description:
            "We automatically retrieves all trade information in one location, allowing you to view key metrics such as price, fees, and funding.",
        },
        {
          icon: "ion-ios-color-wand-outline",
          title: "Trade Reconciliation vs Exchanges and the Blockchain",
          description:
            "Our Reconciliation module allows you to adjust for trade breaks by reconciling across exchanges and the Blockchain.",
        },
        {
          icon: "ion-ios-checkmark-outline",
          title: "Balances, positions, and reconciliation",
          description:
            "We know where your balances stand across all counterparts, at all times: Custodians, Administrators, Exchanges and wallets.",
        },
        // {
        //   icon: "ion-ios-photos-outline",
        //   title: "Perfect Showcase",
        //   description: "Template makes your website look beautiful.",
        // },
        // {
        //   icon: "ion-ios-videocam-outline",
        //   title: "Video Animation",
        //   description: "You can also add videos to the website as you need.",
        // },
      ],
    };
  },
};
</script>
