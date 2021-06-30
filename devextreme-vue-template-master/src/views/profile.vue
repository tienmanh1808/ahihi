<template>
  <div>
    <h2 class="content-block">Profile</h2>

    <div class="content-block dx-card responsive-paddings">
      <div class="form-avatar">
        <img :src="imageSrc" />
      </div>
      <span>{{ formData.Notes }}</span>
    </div>

    <div class="content-block dx-card responsive-paddings">
      <dx-form
        id="form"
        label-location="top"
        :form-data="formData"
        :colCountByScreen="colCountByScreen"
      />
    </div>
  </div>
</template>

<script>
import DxForm from "devextreme-vue/form";

export default {
  props: {
    picture: String
  },
  data() {
    const picture = "images/employees/01.png";
    return {
    
    imageSrc: `https://js.devexpress.com/Demos/WidgetsGallery/JSDemos/${picture}`,
      formData: {
        ID: 7,
        FirstName: "Mạnh",
        LastName: "Nguyễn ",
        Prefix: "Mr.",
        Position: "Controller",
        Picture: picture,
        BirthDate: new Date("1999/08/18"),
        HireDate: new Date("2005/05/11"),
        Notes:

          "Tôi là Mạnh " +
          "Rất vui đc làm quen" +
          "\r\n\r\n" +
          "ahihi.",
        Address: "Hà Nội."
      },
      colCountByScreen: {
        xs: 1,
        sm: 2,
        md: 3,
        lg: 4
      }
    };
  },
  components: {
    DxForm
  }
};
</script>

<style lang="scss">
.form-avatar {
  float: left;
  height: 120px;
  width: 120px;
  margin-right: 20px;
  border: 1px solid rgba(0, 0, 0, 0.1);
  background-size: contain;
  background-repeat: no-repeat;
  background-position: center;
  background-color: #fff;
  overflow: hidden;

  img {
    height: 120px;
    display: block;
    margin: 0 auto;
  }
}
</style>
