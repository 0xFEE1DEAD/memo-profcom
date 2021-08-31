<template>
  <div class="contact_block">
    <div :class="{'contact_block_avatar_block': true, 'small-avatar': small}">
      <img alt="Фото" class="contact_block_avatar_block_image" :src="resolve_img_url(avatar_src)">
    </div>
    <div :class="{'contact_block_contacts': true, 'contact_block_contacts-sm': small}">
      <div :class="{'contact_block_contacts_full-name': true, 'fullname-small': small}"><slot name="fullname"></slot></div>
      <div :class="{'contact_block_contacts_position': true, 'position-small': small}"><slot name="position"></slot></div>
      <div :class="{'contact_block_contacts_contacts': true, 'contacts-small': small}"><slot name="contacts"></slot></div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'contact-block',
  props: {
    avatar_src: {
      type: String,
      default: 'photo.png'
    },
    small: {
      type: Boolean,
      default: false
    }
  },
  methods: {
    resolve_img_url(path) {
      let images = require.context('../assets/images', false, /\.png$|\.jpg$/)
      return images("./" + path)
    }
  }
}
</script>

<style scoped>
  .contact_block {
    align-items: center;
    display: inline-flex;
    margin: 5px;
  }

  .contact_block_avatar_block {
    height: 100px;
    display: inline-block;
  }

  .contact_block_contacts {
    margin-left: 30px;
    display: inline-block;
  }

  .contact_block_contacts-sm {
    margin-left: 20px;
  }

  .contact_block_avatar_block_image {
    width: auto;
    height: 100%;
    border-radius: 100%;
    border: solid 2px white;
  }

  .contact_block_contacts_full-name {
    font-family: 'Bebas Neue';
    font-weight: 400;
    font-size: 28px;
  }

  .fullname-small {
    font-size: 23px;
  }

  .contact_block_contacts_position {
    font-family: 'Bebas Neue';
    font-weight: 400;
    font-size: 17px;
    margin-top: -5px;
    color: #333;
  }

  .position-small {
    font-size: 18px;
  }

  .contact_block_contacts_contacts {
    font-family: 'Bebas Neue';
    font-weight: 400;
    font-size: 26px;
    margin-top: 5px;
  }

  .contacts-small {
    font-size: 23px;
  }

  .small-avatar {
    height: 70px;
  }

  @media (max-width: 880px) {
    .contact_block_contacts {
      margin-left: 25px;
    }

    .contact_block_avatar_block {
      height: 80px;
    }

    .contact_block_contacts_full-name {
      font-size: 24px;
    }

    .contact_block_contacts_position {
      margin-top: -3px;
      font-size: 15px;
    }

    .contact_block_contacts_contacts {
      margin-top: 3px;
      font-size: 22px;
    }

    .contact_block_contacts-sm {
      margin-left: 15px;
    }

    .small-avatar {
      height: 60px;
    }

    .fullname-small {
      font-size: 20px;
    }

    .position-small {
      font-size: 16px;
    }

    .contacts-small {
      font-size: 18px;
    }
  }

  @media (max-width: 350px) {
    .contact_block_contacts {
      margin-left: 20px;
    }

    .contact_block_avatar_block {
      height: 60px;
    }

    .contact_block_contacts_full-name {
      font-size: 20px;
    }

    .contact_block_contacts_position {
      margin-top: -2px;
      font-size: 12px;
    }

    .contact_block_contacts_contacts {
      margin-top: 2px;
      font-size: 16px;
    }

    .contact_block_contacts-sm {
      margin-left: 14px;
    }

    .small-avatar {
      height: 50px;
    }

    .fullname-small {
      font-size: 18px;
    }

    .position-small {
      font-size: 16px;
    }

    .contacts-small {
      font-size: 16px;
    }
  }
</style>
