<script lang="ts">
import Input from "./Input.vue";
import Range from "./Range.vue";
import Textarea from "./Textarea.vue";
import Checkbox from "./Checkbox.vue";
import Radio from "./Radio.vue";
import { defineComponent, ref } from "vue";

export default defineComponent({
  name: "form-tes",
  components: {
    Input,
    Textarea,
  },
  setup(porps, { emit }) {
    const formData = ref({
      jobTitle: "",
      keterangan: "",
    });

    const handleSave = () => {
      console.log("coba..", formData.value);
    };

    const handleInput = (e: any) => {
    const input = e.target.value;
   console.log("handle input...", input);
};


    return {
      formData,
      handleSave,
      handleInput,
    };
  },

});
</script>

<template>
  <form
  @submit.prevent="handleSave" 
  class="flex flex-col gap-5 py-1 mx-auto my-0 w-[60%]">
    <h2 class="text-1xl font-bold text-bg">Personal Details</h2>
    <div class="grid gap-5 mb-6 md:grid-cols-2">
      <div className="flex flex-row items-center">
        <Input label="Wanted Job Title" placeholder="Software Engineer" name="jobTitle" v-model="formData.jobTitle" onchange="handleInput"  type="text"></Input>
      </div>
      <div className="flex flex-row items-center">
        <Input label="Upload Foto" name="email" type="file"></Input>
      </div>
      <div className="flex flex-row items-center">
        <Input label="First Name" placeholder="Anton" name="firstName" type="text"></Input>
      </div>
      <div className="flex flex-row items-center">
        <Input label="Last Name" placeholder="Liandi" name="lastName" type="text"></Input>
      </div>
      <div className="flex flex-row items-center">
        <Input label="E-mail" placeholder="anton@gmail.com" name="email" type="email"></Input>
      </div>
      <div className="flex flex-row items-center">
        <Input label="Phone" placeholder="098762829" name="phoneNumber" type="number"></Input>
      </div>
      <div className="flex flex-row items-center">
        <Input label="Country" placeholder="Indo" name="country" type="text"></Input>
      </div>
      <div className="flex flex-row items-center">
        <Input label="City" placeholder="Jakarta" name="city" type="text"></Input>
      </div>
      <div className="flex flex-row items-center">
        <Input label="Address" placeholder="Jl Sumantri" name="address" type="text"></Input>
      </div>
      <div className="flex flex-row items-center">
        <Input label="Postal Code" placeholder="33012" name="postalCOde" type="text"></Input>
      </div>
      <div className="flex flex-row items-center">
        <Input label="Driving License" placeholder="" name="drivingLicense" type="text"></Input>
      </div>
      <div className="flex flex-row items-center">
        <Input label="Nationality" placeholder="" name="nationality" type="text"></Input>
      </div>
      <div className="flex flex-row items-center">
        <Input label="Place Of Birth" placeholder="" name="placeBirth" type="text"></Input>
      </div>
      <div className="flex flex-row items-center">
        <Input label="Date Of Birth" placeholder="" name="dateBirth" type="date"></Input>
      </div>
    </div>
    <div class="gap-5 mb-1 md:grid-cols-1">
      <h2 class="text-2xl font-bold dark:text-bgVar">Professional Summary</h2>
        <p class="my-4 text-sm text-gray-100">Write 2-4 short & energetic sentences to interest the reader! Mention your role. experience & most importantly - your biggest achievment. best qualities and skils</p>
        <div className="flex flex-row items-center">
        <Textarea placeholder="" name="dateBirth" type="textarea"></Textarea>
      </div>
    </div>
    <div class="gap-5 mb-1 md:grid-cols-1">
      <h2 class="text-2xl font-bold dark:text-bgVar">Employment History</h2>
        <p class="my-4 text-sm text-gray-700">Show your relevant experience (last 10 years). Use bullet points to note yaou achievment, if possible - use number/facts (Achievment X, measured by Y, by doing Z)</p>
    </div>
    <div class="grid gap-5 mb-6 md:grid-cols-2">
      <div className="flex flex-row items-center">
        <Input label="Job Title" placeholder="" name="jobTitle" type="text"></Input>
      </div>
      <div className="flex flex-row items-center">
        <Input label="Employer" placeholder="" name="employer" type="text"></Input>
      </div>
      <div className="flex-row items-center">
        <div class="grid gap-11 mb-6 md:grid-cols-2">
          <div className="flex flex-row items-center">
            <Input label="Start Date" placeholder="" name="startDate" type="date"></Input>
          </div>
          <div className="flex flex-row items-center">
            <Input label="End Date" placeholder="" name="endDate" type="date"></Input>
          </div>
        </div>
      </div>
      <div className="flex flex-row items-center pb-6">
        <Input label="City" placeholder="" name="cityEmployment" type="text"></Input>
      </div>
    </div>
    <div class="grid mb-6 md:grid-cols-1">
      <div className="flex flex-row items-center">
        <Textarea label="Description" placeholder="" name="description" type="text"></Textarea>
      </div>
      <p class="my-4 text-sm text-gray-700">Recruiter tip: write 200+ characters to increase interview chances</p>
    </div>
    <div class="gap-5 mb-1 md:grid-cols-1">
      <h2 class="text-2xl font-bold dark:text-bgVar">Education</h2>
        <p class="my-4 text-sm text-gray-700">A varied on your resume sums up the value that your learnings and background will bring to job</p>
    </div>
    <div class="grid gap-5 mb-6 md:grid-cols-2">
      <div className="flex flex-row items-center">
        <Input label="School" placeholder="" name="school" type="text"></Input>
      </div>
      <div className="flex flex-row items-center">
        <Input label="Degree" placeholder="" name="degree" type="text"></Input>
      </div>
      <div className="flex-row items-center">
        <div class="grid gap-11 mb-6 md:grid-cols-2">
          <div className="flex flex-row items-center">
            <Input label="Start Date" placeholder="" name="startDateEdu" type="date"></Input>
          </div>
          <div className="flex flex-row items-center">
            <Input label="End Date" placeholder="" name="endDateEdu" type="date"></Input>
          </div>
        </div>
      </div>
      <div className="flex flex-row items-center pb-6">
        <Input label="City" placeholder="" name="cityEdu" type="text"></Input>
      </div>
    </div>
    <div class="grid mb-6 md:grid-cols-1">
      <div className="flex flex-row items-center">
        <Textarea label="Description" placeholder="" name="description" type="text"></Textarea>
      </div>
    </div>
    <div class="gap-5 mb-1 md:grid-cols-1">
      <h2 class="text-2xl font-bold dark:text-bgVar">Skills</h2>
        <p class="my-4 text-sm text-gray-700">Choose 5 of the most important skills to show your talent! Make sure they match the keywords of the job listening if applying via an online system</p>
    </div>
    <div class="grid gap-5 mb-6 md:grid-cols-7">
      <div className="flex flex-row items-center">
        <button
        disabled
        class="px-4 py-2 rounded bg-primaryVar font-semibold text-sm cursor-pointer transition-colors hover:bg-fgVar"
      >
        Java
      </button>
      </div>
      <div className="flex flex-row items-center">
        <button
        disabled
        class="px-4 py-2 rounded bg-primaryVar font-semibold text-sm cursor-pointer transition-colors hover:bg-fgVar"
      >
        Javascript
      </button>
      </div>
      <div className="flex flex-row items-center">
        <button
        disabled
        class="px-4 py-2 rounded bg-primaryVar font-semibold text-sm cursor-pointer transition-colors hover:bg-fgVar"
      >
        python
      </button>
      </div>
      <div className="flex flex-row items-center">
        <button
        disabled
        class="px-4 py-2 rounded bg-primaryVar font-semibold text-sm cursor-pointer transition-colors hover:bg-fgVar"
      >
        Git
      </button>
      </div>
      <div className="flex flex-row items-center">
        <button
        disabled
        class="px-4 py-2 rounded bg-primaryVar font-semibold text-sm cursor-pointer transition-colors hover:bg-fgVar"
      >
        SQL
      </button>
      </div>
      <div className="flex flex-row items-center">
        <button
        disabled
        class="px-4 py-2 rounded bg-primaryVar font-semibold text-sm cursor-pointer transition-colors hover:bg-fgVar"
      >
        C++
      </button>
      </div>
      <div className="flex flex-row items-center">
        <button
        disabled
        class="px-4 py-2 rounded bg-primaryVar font-semibold text-sm cursor-pointer transition-colors hover:bg-fgVar"
      >
        Typescript
      </button>
      </div>
      <div className="flex flex-row items-center">
        <button
        disabled
        class="px-4 py-2 rounded bg-primaryVar font-semibold text-sm cursor-pointer transition-colors hover:bg-fgVar"
      >
        C#
      </button>
      </div>
      <div className="flex flex-row items-center">
        <button
        disabled
        class="px-4 py-2 rounded bg-primaryVar font-semibold text-sm cursor-pointer transition-colors hover:bg-fgVar"
      >
        Docker
      </button>
      </div>
      <div className="flex flex-row items-center">
        <button
        disabled
        class="px-4 py-2 rounded bg-primaryVar font-semibold text-sm cursor-pointer transition-colors hover:bg-fgVar"
      >
        PHP
      </button>
      </div>
      <div className="flex flex-row items-center">
        <button
        disabled
        class="px-4 py-2 rounded bg-primaryVar font-semibold text-sm cursor-pointer transition-colors hover:bg-fgVar"
      >
        React
      </button>
      </div>
      <div className="flex flex-row items-center">
        <button
        disabled
        class="px-4 py-2 rounded bg-primaryVar font-semibold text-sm cursor-pointer transition-colors hover:bg-fgVar"
      >
        MongoDB
      </button>
      </div>
      <div className="flex flex-row items-center">
        <button
        disabled
        class="px-4 py-2 rounded bg-primaryVar font-semibold text-sm cursor-pointer transition-colors hover:bg-fgVar"
      >
        Toad
      </button>
      </div>
    </div>
    <div>
      <span class="flex w-full justify-end gap-4">
      <button
        disabled
        class="px-4 py-2 rounded bg-fgVar font-semibold text-sm cursor-pointer transition-colors hover:bg-fgVar"
      >
        Cancel
      </button>
      <button
        type="submit"
        class="px-4 py-2 rounded bg-primary font-semibold text-sm cursor-pointer transition-colors hover:bg-primaryVar"
      >
        Save
      </button>
    </span>
    </div>
  </form>
</template>
