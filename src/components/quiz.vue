<template>
  <div>
    <div class="quiz-container">
      <div class="paragraph">
        <p>
          At the bottom left of the presentation, you should see controls to
          move back and forward between slides. To listen to the sound byte, tap
          on the button in the middle of the slide. Alternatively, hover your
          mouse over it to show scroll bar and play button.
        </p>
      </div>

      <iframe
        src="https://docs.google.com/presentation/d/e/2PACX-1vRvDMtM53cfYPquV9JAIp9WOPlrl4VkV7aEbnUqDluxfeRsIFbPu8DtSeBQgoixDyyuMMXMgQRP-5AY/embed?start=false&loop=false&delayms=60000"
        frameborder="0"
        allowfullscreen="true"
        mozallowfullscreen="true"
        webkitallowfullscreen="true"
      ></iframe>

      <div class="thanks" v-if="loading">
        <h1>Thanks! I've got your answers and will have a look soon :)</h1>
      </div>

      <form name="submitting" v-if="!loading">
        <div>
          <label for="q1">Question 1</label>
          <input type="text" name="q1" />
          <label for="q2">Question 2</label>
          <input type="text" name="q2" />
          <label for="q3">Question 3</label>
          <input type="text" name="q3" />
          <label for="q4">Question 4</label>
          <input type="text" name="q4" />
          <label for="q5">Question 5</label>
          <input type="text" name="q5" />
          <label for="q6">Question 6</label>
          <input type="text" name="q6" />
          <label for="q7">Question 7</label>
          <input type="text" name="q7" />
          <label for="q8">Question 8</label>
          <input type="text" name="q8" />
          <label for="q9">Question 9</label>
          <input type="text" name="q9" />
          <label for="q10">Question 10</label>
          <input type="text" name="q10" />
        </div>
        <div>
          <label for="q11">Question 11</label>
          <input type="text" name="q11" />
          <label for="q12">Question 12</label>
          <input type="text" name="q12" />
          <label for="q13">Question 13</label>
          <input type="text" name="q13" />
          <label for="q14">Question 14</label>
          <input type="text" name="q14" />
          <label for="q15">Question 15</label>
          <input type="text" name="q15" />
          <label for="q16">Question 16</label>
          <input type="text" name="q16" />
          <label for="q17">Question 17</label>
          <input type="text" name="q17" />
          <label for="q18">Question 18</label>
          <input type="text" name="q18" />
          <label for="q19">Question 19</label>
          <input type="text" name="q19" />
          <label for="q20">Question 20</label>
          <input type="text" name="q20" />
          <label for="q21">Question 21</label>
          <input type="text" name="q21" />
        </div>
        <br />
        <input class="submit" type="submit" value="SUBMIT" @click="handleFormSubmit()" />
      </form>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      loading: false
    };
  },
  methods: {
    handleFormSubmit() {
      event.preventDefault();
      const scriptURL =
        "https://script.google.com/macros/s/AKfycbxaEdLo1cDY9QJS235PfcJ7C3q25Hk0NubZ3YutyannfiAuWGU/exec";
      const form = document.forms["submitting"];

      if (event) {
        fetch(scriptURL, { method: "POST", body: new FormData(form) })
          .then((this.loading = true))
          .catch(error => console.error("Error!", error.message));
      }
    }
  }
};
</script>
