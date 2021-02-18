<template>
  <v-container   fluid>
    <v-row align="center">
      <v-col
        class="d-flex"
        cols="12"
        sm="6"
        >
        <v-select
          outlined
          v-model="userInfo.jobType"
          :items="jobTypes"
          :rules="[rules.required]"
          label="متقاضی کدام یک از مشاغل زیر هستید"
          ></v-select>
      </v-col>
    </v-row>
    <v-row align="center">
        <v-col
          class="d-flex"
          cols="12"
          sm="4"
          >
          <v-text-field
          outlined
            v-model="userInfo.firstName"
          :rules="[rules.required]"
          label="نام"
          ></v-text-field>
        </v-col>
        <v-col
          class="d-flex"
          cols="12"
          sm="4"
          >
          <v-text-field
          outlined
            v-model="userInfo.lastName"
          :rules="[rules.required]"
          label="نام خانوادگی"
          ></v-text-field>
        </v-col>
        <v-col
          class="d-flex"
          cols="12"
          sm="4"
          >
          <v-text-field
          outlined
            v-model="userInfo.nationalCode"
          :rules="[rules.required]"
          label="کد ملی"
          ></v-text-field>
        </v-col>
    </v-row>
    <v-row align="center">
        <v-col
          class="d-flex"
          cols="12"
          sm="3"
          >
          <v-select
          outlined
          v-model="userInfo.birthProvince"
          :rules="[rules.required]"
          :items="provinces"
          label="استان محل تولد"
          ></v-select>
        </v-col>
        <v-col
          class="d-flex"
          cols="12"
          sm="3"
          >
          <v-select
          outlined
          v-model="userInfo.maritalStatus"
          :rules="[rules.required]"
          :items="maritalStatuses"
          label="وضعیت تاهل"
          ></v-select>
        </v-col>
        <v-col
          class="d-flex"
          cols="12"
          sm="3"
          >
          <v-select
          outlined
          v-model="userInfo.sex"
          :rules="[rules.required]"
          :items="gender"
          label="جنسیت"
          ></v-select>
        </v-col>
        <v-col
          class="d-flex"
          cols="12"
          sm="3"
          >
          <v-text-field
          outlined
            v-model="userInfo.phoneNumber"
          :rules="[rules.required]"
          label="شماره تلفن همراه"
          ></v-text-field>
        </v-col>
    </v-row>
    <v-row align="center">
        <v-col
          class="d-flex"
          cols="12"
          sm="3"
          >
          <v-select
          outlined
          v-model="userInfo.addressProvince"
          :rules="[rules.required]"
          :items="provinces"
          label="استان محل سکونت"
          ></v-select>
        </v-col>
        <v-col
          class="d-flex"
          cols="12"
          sm="3"
          >
          <v-text-field
          outlined
            v-model="userInfo.city"
          :rules="[rules.required]"
          label="شهر محل سکونت"
          ></v-text-field>
        </v-col>
        <v-col
          class="d-flex"
          cols="12"
          sm="6"
          >
          <v-text-field
          outlined
            v-model="userInfo.address"
          :rules="[rules.required]"
          label="آدرس"
          ></v-text-field>
        </v-col>
    </v-row>
    <v-row align="center">
        <v-col
          class="d-flex"
          cols="12"
          sm="3"
          >
          <v-select
          outlined
          v-model="userInfo.weight"
          :rules="[rules.required]"
          :items="weights"
          label="وزن"
          ></v-select>
        </v-col>
        <v-col
          class="d-flex"
          cols="12"
          sm="3"
          >
          <v-select
          outlined
          v-model="userInfo.tall"
          :rules="[rules.required]"
          :items="talls"
          label="قد"
          ></v-select>
        </v-col>
        <v-col
          class="d-flex"
          cols="12"
          sm="3"
          >
          <v-select
          outlined
          v-model="userInfo.age"
          :items="ages"
          :rules="[rules.required]"
          label="سن"
          ></v-select>
        </v-col>
        <v-col
          class="d-flex"
          cols="12"
          sm="3"
          >
          <v-select
          outlined
          v-model="userInfo.education"
          :rules="[rules.required]"
          :items="educations"
          label="تحصیلات"
          ></v-select>
        </v-col>
    </v-row>
    <v-row align="center">
        <v-col
          class="d-flex"
          cols="12"
          sm="4"
          >
          <v-select
          outlined
          v-model="userInfo.eyeEarStatus"
          :rules="[rules.required]"
          :items="eyeEarStates"
          label="وضعیت بینایی و شنوایی"
          ></v-select>
        </v-col>
        <v-col
          class="d-flex"
          cols="12"
          sm="4"
          >
          <v-select
          outlined
          v-model="userInfo.sickness"
          :rules="[rules.required]"
          :items="yesOrNo"
          label="آیا بیماری خاصی دارید؟"
          ></v-select>
        </v-col>
        <v-col
          class="d-flex"
          cols="12"
          sm="4"
          >
          <v-select
          outlined
          v-model="userInfo.smocking"
          :rules="[rules.required]"
          :items="yesOrNo"
          label="آیا سیگار و دخانیات مصرف می کنید؟"
          ></v-select>
        </v-col>
    </v-row>
    <v-row align="center">
        <v-col
          class="d-flex"
          cols="12"
          sm="4"
          >
          <v-select
          outlined
          v-model="userInfo.working"
          :rules="[rules.required]"
          :items="works"
          label="وضعیت اشتغال در حال حاضر"
          ></v-select>
        </v-col>
        <v-col
          class="d-flex"
          cols="12"
          sm="4"
          >
          <v-select
          outlined
          v-model="userInfo.expertField"
          :rules="[rules.required]"
          :items="experinceFields"
          label="در چه زمینه ای تخصص دارید"
          ></v-select>
        </v-col>
        <v-col
          class="d-flex"
          cols="12"
          sm="4"
          >
          <v-select
          outlined
          v-model="userInfo.englishLevel"
          :rules="[rules.required]"
          :items="englishLevels"
          label="سطح آشنایی به زبان انگلیسی"
          ></v-select>
        </v-col>
    </v-row>
    <v-row align="center">
        <v-col
          class="d-flex"
          cols="12"
          sm="2"
          >
          <v-select
          outlined
          v-model="userInfo.experience"
          :rules="[rules.required]"
          :items="yesOrNo"
          label="آیا سابقه کار دارید؟"
          ></v-select>
        </v-col>
        <v-col
          class="d-flex"
          cols="12"
          sm="4"
          >
          <v-select
          outlined
          v-model="userInfo.arresting"
          :rules="[rules.required]"
          :items="yesOrNo"
          label="آیا سابقه دستگیری یا محکومیت کیفری دارید؟"
          ></v-select>
        </v-col>
        <v-col
          class="d-flex"
          cols="12"
          sm="6"
          >
          <v-select
          outlined
          v-model="userInfo.sponser"
          :rules="[rules.required]"
          :items="yesOrNo"
          label="بابت تضمین عملکرد خود حداقل یک نفر ضامن معتبر دارید؟"
          ></v-select>
        </v-col>
    </v-row>
    <v-row align="center">
        <v-col
          class="d-flex text-center"
          cols="12"
          sm="12"
          >
          <v-btn
            :loading="isLoading"
            class="mx-auto"
            color="primary"
            elevation="3"
            x-large
            @click="makePdf"
            >
            <h2 id="file">ثبت</h2>
          </v-btn>
        </v-col>
    </v-row>
    <v-snackbar
      :timeout="2000"
      v-model="snackbar"
    >
      {{ message }}
    </v-snackbar>
  </v-container>
</template>

<script>
export default {
  name: 'Questionnaire',
  data() {
    return {
      isLoading: false,
      message: null,
      snackbar: false,
      rules: {
        required: value => !!value || 'این فیلد اجباری است',
      },
      userInfo: {
        firstName: null,
        lastName: null,
        birthProvince: null,
        nationalCode: null,
        addressProvince: null,
        city: null,
        address: null,
        maritalStatus: null,
        age: null,
        weight: null,
        tall: null,
        eyeEarStatus: null,
        sickness: null,
        smocking: null,
        education: null,
        working: null,
        expertField: null,
        englishLevel: null,
        experience: null,
        arresting: null,
        sponser: null
      },
      maritalStatuses: [
        'مجرد',
        'متاهل'
      ],
      ages: [
        '۱۸-۲۴',
        '۲۵-۳۴',
        '۳۵-۴۴',
        '۴۵-۵۴',
        '۵۵-۶۴',
        'بالای ۶۵',
      ],
      jobTypes: [
        'کارگر تولید',
        'کارگر واحد بسته بندی',
        'حسابدار',
        'نیروی نگهبان',
        'کارگر خدمات',
        'تکنسین مکانیک',
        'تکنسین تاسیسات',
        'کارمند فروش (بازاریاب)',
        'کارگر ساده (بارگیری کالا)',
        'باغبان',
        'متصدی امور اداری',
        'راننده پایه ۲',
        'سایر مشاغل'
      ],
      gender: [
        'مرد',
        'زن'
      ],
      eyeEarStates: [
        'هر دو سالم',
        'دچار مشکل شنوایی هستم',
        'از عینک استفاده می کنم',
        'عینک و مشکل شنوایی دارم'
      ],
      provinces: [
        'آذربايجان شرقي',
        'آذربايجان غربي',
        'اردبيل',
        'اصفهان',
        'البرز',
        'ايلام',
        'بوشهر',
        'تهران',
        'چهارمحال و بختياري',
        'خراسان جنوبي',
        'خراسان رضوي',
        'خراسان شمالي',
        'خوزستان',
        'زنجان',
        'سمنان',
        'سيستان و بلوچستان',
        'فارس',
        'قزوين',
        'قم',
        'كردستان',
        'كرمان',
        'كرمانشاه',
        'كهگيلويه و بويراحمد',
        'گلستان',
        'گيلان',
        'لرستان',
        'مازندران',
        'مركزي',
        'هرمزگان',
        'همدان',
        'یزد'
      ],
      weights: [
        'زیر ۶۰ کیلوگرم',
        '۶۰-۶۵ کیلو گرم',
        '۶۶-۷۰ کیلوگرم',
        '۷۱-۷۵ کیلوگرم',
        '۷۶-۸۰ کیلوگرم',
        '۸۱-۸۵ کیلوگرم',
        '۸۶-۹۰ کیلوگرم',
        '۹۱-۹۵ کیلوگرم',
        '۹۶-۱۰۰ کیلوگرم',
        '۱۰۱-۱۰۵ کیلوگرم',
        '۱۰۶-۱۱۰ کیلوگرم',
        'بالای ۱۱۰ کیلوگرم'
      ],
      talls: [
        'زیر ۱۶۰ سانتی متر',
        '۱۶۱-۱۶۵ سانتی متر',
        '۱۶۶-۱۷۰ سانتیمتر',
        '۱۷۱-۱۷۵ سانتی متر',
        '۱۷۶-۱۸۰ سانتی متر',
        '۱۸۱-۱۸۵ سانتی متر',
        '۱۸۶-۱۹۰ سانتی متر',
        '۱۹۱-۱۹۵ سانتی متر',
        'بالای ۱۹۵ سانتی متر'
      ],
      yesOrNo: [
        'بله',
        'خیر'
      ],
      educations: [
        'زیر دیپلم',
        'دیپلم',
        'فوق دیپلم',
        'کارشناسی',
        'کارشناسی ارشد',
        'دکترا'
      ],
      works: [
        'کارمند پاره وقت',
        'مغازه دار',
        'دانشجو',
        'بیکار',
        'بازنشسته',
        'کارمند'
      ],
      experinceFields: [
        'باغبانی',
        'پرستاری',
        'بهیاری',
        'کمک بهیاری',
        'فروش و بازاریابی',
        'امور اداری و کارگزینی',
        'امور مالی و حسابداری',
        'تاسیسات و امور فنی',
        'نگهبانی و حراست',
        'الکترونیک و کامپیوتر',
        'کارگری',
        'عمرانی و ساخت و ساز',
        'سایر موارد'
      ],
      englishLevels: [
        'ضعیف',
        'متوسط',
        'خوب'
      ]
    }
  },
  computed: {
    isValid() {
      return Object.keys(this.userInfo).filter(key => this.userInfo[key] === null ||
        this.userInfo[key] === undefined || this.userInfo[key] === "").length == 0
    }
  },
  methods: {
    makePdf() {
      if (!this.isValid) {
        this.message = 'لطفا تمام فیلد ها را  پر کنید'
        this.snackbar = true
      } else {
        this.isLoading = true
        console.log(this.userInfo)
        fetch('https://webapi.ghadergostaran.com/pdf', {
          method: 'POST',
          headers: {
            'Content-Type': 'application/json'
          },
          body: JSON.stringify(this.userInfo)
        })
          .then(response => { response.json()
            this.isLoading = false
            this.message = 'اطلاعات شما ارسال شد'
            this.snackbar = true
          })
      }
    }
  }
}
</script>

