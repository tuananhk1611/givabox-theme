<template>
  <div id="about-us-page" class="about-us-page">
    <div class="container">
      <div class="row">
        <div class="col-12 col-sm-8 figure-about">
          <img src="../../assets/images/about-giva.png" alt="about-midsleek">
        </div>
        <div class="col-12">
          <div class="about-us-content">
            <div class="row">
              <div class="col-12 col-sm-8 content-text-about">
                <h1 class="h1 heading-section-giva">
                  Who doesn’t like receiving gifts, especially cool ones?
                </h1>
                <p class="mb32">
                  Since we believe in the true meaning of giving love and receiving it back, we really love surprising our family and friends with unique special gifts on every occasion. While always seeking the coolest gifts, we’ve found so many great products that we want to share with people like us.
                </p>
                <p class="mb32">
                  Therefore, Givabox was born as a place to share every passion and interest on Earth because it is a reference to your love and happiness. And to spread exactly that is our core vision: To help you Give a Happy Box to people who you love.
                </p>
                <p class="mb32">
                  No matter where you are, who you are and what you are passionate about, we want to be able to provide you with custom products that express your true self! That's why at Givabox.co you will find a special collection for every profession, hobby, sport, passion or anything you might think of. So whatever you're looking for, we plan to have it there for you.
                </p>
                <p class="mb32">
                  Since we know you want perfect gifts for your beloved ones, our team has partnered up with the most professional suppliers and put the product quality on top.
                </p>
                <p class="mb24">
                  We love to help you deliver happiness for a lifetime.
                </p>
                <p class="sign-text">
                  Enjoy giving happy boxes with us!
                </p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
    <Newsletter
      v-if="newsletterSettings"
      :key="newsletterSettings.id"
      :settings="newsletterSettings.settings"
      :data-id="newsletterSettings.id"
    />
  </div>
</template>

<script>
import { getCoreMixin } from '../../shared/mixin'
import Breadcrumbs from '../../components/Breadcrumbs'
import BaseInput from '../../components/BaseInput'
import BaseTextarea from '../../components/BaseTextarea'
import Newsletter from '../../sections/Home/Newsletter'

export default {
  name: 'TemplatePageAboutUs',
  components: {
    Breadcrumbs,
    BaseInput,
    BaseTextarea,
    Newsletter
  },
  mixins: [getCoreMixin('contactUsMixin')],
  props: {
    page: {
      type: Object,
      default: () => {},
    },
    bodyHtml: {
      type: String,
      default: '',
    },
    routes: {
      type: Array,
      default: () => [],
    },
  },
  computed: {
    newsletterSettings() {
      const setting = this.$getPageSettings('homepage').filter((setting) => setting.type === 'newsletter')
      if (setting && setting.length > 0) return setting[0]
      return null
    },
  },
}
</script>
