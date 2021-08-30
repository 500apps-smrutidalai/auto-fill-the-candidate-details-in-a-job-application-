<template>
  <div class="container pt-3">
    <b-form @submit="onSubmit" @reset="onReset" v-if="show">
      <b-row style="display: flex">
        <div class="col-md-6">
          <b-form-input
            id="input-2"
            v-model="form.name"
            placeholder="Enter name"
            required
          ></b-form-input>
        </div>
        <br />
        <div class="col-md-6">
          <b-form-input
            type="email"
            id="input-2"
            v-model="form.email"
            placeholder="Enter first name"
            required
          ></b-form-input>
        </div>
        <br />
      </b-row>
      <b-row style="display: flex; padding-top: 15px">
        <div class="col-md-6" style="padding-top: 15px">
          <b-form-input
            id="input-2"
            v-model="form.contact"
            placeholder="Enter contact number"
            required
          ></b-form-input
          ><br />
        </div>
        <div class="col-md-6">
          <b-form-file
            v-model="upload_file"
            :state="Boolean(upload_file)"
            drop-placeholder="Drop file here..."
          ></b-form-file>
        </div>
        <br />

        <br />
        <div>
          <b-form-checkbox
            id="checkbox-1"
            v-model="form.persnol_info"
            name="checkbox-1"
            value="accepted"
            unchecked-value="not_accepted"
            style="float: left"
            >Basic Information
          </b-form-checkbox>
          <div v-if="form.persnol_info === 'accepted'">
            <b-form-input
              type="date"
              id="input-2"
              v-model="form.dob"
              placeholder="Enter Date of birth"
              required
            ></b-form-input>

            <b-form-input
              id="input-2"
              v-model="form.experience"
              placeholder="Enter Experience"
              required
            ></b-form-input
            ><br />
          </div>

          <b-form-checkbox
            id="checkbox-2"
            v-model="form.skills_info"
            name="checkbox-2"
            value="accept"
            unchecked-value="not_accept"
            style="float: left; padding-left: 30px"
            >Skills And Work Experience
          </b-form-checkbox>
          <div v-if="form.skills_info === 'accept'">
            <b-form-input
              id="input-2"
              v-model="form.cource"
              placeholder="skill1"
              required
            ></b-form-input>

            <b-form-input
              id="input-2"
              v-model="form.skill_experience"
              placeholder="Enter Experience"
              required
            ></b-form-input
            ><br />
          </div>

          <b-form-checkbox
            id="checkbox-3"
            v-model="form.education_info"
            name="checkbox-3"
            value="accept1"
            unchecked-value="not_accept1"
            style="float: left; padding-left: 30px"
            >cource
          </b-form-checkbox>
          <div v-if="form.education_info === 'accept1'">
            <b-form-input
              id="input-2"
              v-model="form.education"
              placeholder="Enter cource"
              required
            ></b-form-input>

            <label></label>
            <b-form-input
              id="input-2"
              v-model="form.experience"
              placeholder="Enter Experience"
              required
            ></b-form-input
            ><br />
          </div>
        </div>
      </b-row>

      <b-button type="submit" variant="primary">Submit</b-button>
      <b-button type="reset" variant="danger">Reset</b-button>
    </b-form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      form: {
        email: "",
        name: "",
        contact: "",
        persnol_info: "",
        skills_info: "",
        education_info: "",
        dob: "",
        experience: "",
        cource: "",
        skill_experience: "",
        education: "",
      },

      show: true,
    };
  },
  methods: {
    onSubmit(event) {
      event.preventDefault();
      alert(JSON.stringify(this.form));
    },
    onReset(event) {
      event.preventDefault();
      this.form.email = "";
      this.form.name = "";
      this.show = false;
      this.form.education = "";
      this.form.contact = "";
      this.form.persnol_info = "";
      this.form.skills_info = "";
      this.form.skills_info="";
      this.$nextTick(() => {
        this.show = true;
      });
    },
  },
};
</script>