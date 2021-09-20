<template>
  <div class="container">
    <svg class="wave" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1440 320">
      <path
        fill="#C7ACDA"
        fill-opacity="1"
        d="M0,128L60,154.7C120,181,240,235,360,261.3C480,288,600,288,720,288C840,288,960,288,1080,261.3C1200,235,1320,181,1380,154.7L1440,128L1440,0L1380,0C1320,0,1200,0,1080,0C960,0,840,0,720,0C600,0,480,0,360,0C240,0,120,0,60,0L0,0Z"
      ></path>
    </svg>
    <div class="form_container">
      <!-- Container containing Image -->

      <div class="form_container-left">
        <h1 class="mb-3">Sample heading</h1>
        <p>
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Laborum
          distinctio incidunt quae voluptas tempore dolorem, autem officia
          libero soluta.
        </p>
      </div>

      <!-- Container containing Form on the Right side of the image -->

      <div class="form_container-right">
        <form action="/">
          <h2>
            Create an account
          </h2>
          <h3>Enter your email</h3>
          <input type="text" placeholder="Email" required />
          <h4>Date of birth (Optional)</h4>
          <div class="selectDate">
            <div class="date">
              <h5>Date</h5>
              <select name="date" id="date">
                <!-- Using for-loop to inject data dynamicaly -->

                <option v-for="day in days" :key="day" :value="day">
                  {{ day }}
                </option>
                <v-icon>mdi-menu-down</v-icon>
              </select>
            </div>
            <div class="month">
              <h5>Month</h5>
              <select name="month" id="month">
                <v-icon>mdi-menu-down</v-icon>
                <option v-for="month in months" :key="month" :value="month">{{
                  month
                }}</option>
              </select>
            </div>
            <div class="year">
              <h5>Year</h5>
              <select name="year" id="year">
                <option v-for="year in years" :key="year" :value="year">{{
                  year
                }}</option>
              </select>
            </div>
          </div>
          <h3>Chosse a strong password</h3>
          <input type="password" placeholder="Password" required />
          <h3>
            Are you an agency or individual?
          </h3>
          <div class="d-flex">
            <div class="d-flex align-center mr-8">
              <input
                type="radio"
                id="one"
                value="One"
                v-model="picked"
                checked
              />
              <label for="one">Individual</label>
            </div>
            <div class="d-flex align-center mr-8">
              <input type="radio" id="two" value="Two" v-model="picked" />
              <label for="two">Agency</label>
            </div>
          </div>
          <button type="submit">Submit</button>
        </form>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data: () => ({
    selected: "",
    picked: "",
    days: ["01", "02", "03", "04", "05", "06", "07", "08", "09", "10"],
    months: [
      "January",
      "February",
      "March",
      "April",
      "May",
      "Jun",
      "July",
      "August",
      "September",
      "October",
      "November",
      "December",
    ],
    years: [
      "1995",
      "1996",
      "1997",
      "1998",
      "1999",
      "2000",
      "2019",
      "2020",
      "2021",
    ],
  }),
  methods: {
    submit() {},
  },
};
</script>

<style lang="scss" scoped>
// Mobile Breakpoint is 770px

.wave {
  position: absolute;
  height: 65%;
  width: 200%;
  top: -11%;
  left: -46%;

  @media (max-width: 770px) {
    top: -15%;
  }

  @media (max-width: 650px) {
    visibility: hidden;
  }
}

label {
  font: 400 14px/16.41px Roboto;
  color: #666666;
}

button {
  width: 188px;
  height: 44px;
  border-radius: 4px;
  background: #2d9cdb;
  color: white;

  &:hover,
  :active {
    background-color: #69aed6;
  }
}

input[type="radio"] {
  width: 25px;
}

.date {
  width: 65px;
}
.month {
  width: 106px;
  margin: 0px 7px;
}
.year {
  width: 106px;
}

.selectDate {
  display: flex;
  flex-direction: row;
  height: 56px;
}

select {
  height: 37px;
  width: 100%;
  border: 2px solid #bdbdbd;
  border-radius: 3px;
}

input[type="text"],
[type="password"] {
  width: 100%;
  height: 37px;
  border: 2px solid #bdbdbd;
  border-radius: 3px;

  @media (max-width: 650px) {
    height: 52px;
  }

  // &:valid {
  //   border-color: red;
  // }
  // &:required:focus:valid {
  //   border: 1px solid red;
  // }
  // &:focus:invalid {
  //   border: 1px solid red;
  //   background-color: greenyellow;
  // }
}

// .input-container[data-error] .input {
//   border-color: red;
// }

p {
  width: 264px;
  height: 102px;
  padding-left: 10px;
}

.container {
  width: 100%;
  height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

form {
  height: 100%;
  display: flex;
  flex-direction: column;
  justify-content: space-around;
}

.form_container {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 716px;
  height: 513px;
  box-shadow: 0px 15px 30px rgba(0, 0, 0, 0.19);
  border-radius: 5px;
  z-index: 10;

  @media (max-width: 650px) {
    flex-direction: column;
    width: 100%;
    height: 100%;
  }

  &-left {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    width: 361px;
    height: 100%;
    background: chocolate;
    background-image: url("../assets/Img/image.png");
    background-size: cover;

    @media (max-width: 650px) {
      width: 100%;
      height: 270px;
      background-image: url("../assets/Img/Rectangle 2.1 (1).png");
    }
  }

  &-right {
    background: #ffff;
    display: flex;
    flex-direction: column;
    justify-content: space-around;
    width: 399px;
    height: 100%;
    padding: 32px 49px;

    @media (max-width: 650px) {
      width: 100%;
      height: 735px;
    }
  }
}

// Styling for headings

h1 {
  font: 700 34px/39.84px Roboto;
  color: #ffffff;
}

h2 {
  font: 700 24px/28.13px Roboto;
}

h3 {
  font: 700 16px/18.75px Roboto;
}

h4 {
  font: 700 12px/14.06px Roboto;
}

h5 {
  font: 400 14px/16.41px Roboto;
  color: #666666;
}

p {
  font: 500 17px/19.29px Roboto;
  color: #ffffff;
}
</style>
