<template>
  <v-container   fluid>
    <v-row align="center">
      <v-col
        class="d-flex"
        cols="12"
        sm="6"
        >
        <v-select
          v-model="userInfo.jobType"
          :items="jobTypes"
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
            v-model="userInfo.firstName"
          label="نام"
          ></v-text-field>
        </v-col>
        <v-col
          class="d-flex"
          cols="12"
          sm="4"
          >
          <v-text-field
            v-model="userInfo.lastName"
          label="نام خانوادگی"
          ></v-text-field>
        </v-col>
        <v-col
          class="d-flex"
          cols="12"
          sm="4"
          >
          <v-text-field
            v-model="userInfo.nationalCode"
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
          v-model="userInfo.birthProvince"
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
          v-model="userInfo.maritalStatus"
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
          v-model="userInfo.sex"
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
            v-model="userInfo.phoneNumber"
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
          v-model="userInfo.addressProvince"
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
            v-model="userInfo.city"
          label="شهر محل سکونت"
          ></v-text-field>
        </v-col>
        <v-col
          class="d-flex"
          cols="12"
          sm="6"
          >
          <v-text-field
            v-model="userInfo.address"
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
          v-model="userInfo.weight"
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
          v-model="userInfo.tall"
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
          v-model="userInfo.age"
          :items="ages"
          label="سن"
          ></v-select>
        </v-col>
        <v-col
          class="d-flex"
          cols="12"
          sm="3"
          >
          <v-select
          v-model="userInfo.education"
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
          v-model="userInfo.eyeEarStatus"
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
          v-model="userInfo.sickness"
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
          v-model="userInfo.smocking"
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
          v-model="userInfo.working"
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
          v-model="userInfo.expertField"
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
          v-model="userInfo.englishLevel"
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
          v-model="userInfo.experience"
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
          v-model="userInfo.arresting"
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
          v-model="userInfo.sponser"
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
  </v-container>
</template>

<script>
export default {
  name: 'Questionnaire',
  data() {
    return {
      isLoading: false,
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
        'تخصص ندارم',
        'کارگری',
        'امور اداری و کارگزینی',
        'امور مالی و حسابداری',
        'ترابری . حمل بار',
        'نگهبانی و حراست',
        'بهداشت و ایمنی کار',
        'تاسیسات و امور فنی',
        'امور بازرگانی و فروش کالا',
        'الکترونیک و کامپیوتر',
        'امور حقوقی',
        'خدامت عمومی',
        'کارهای هنری',
        'عمرانی و ساخت و ساز',
        'کشاورزی و دام و طیور',
        'فرهنگی',
        'ورزشی',
        'سایر موارد'
      ],
      englishLevels: [
        'ضعیف',
        'متوسط',
        'خوب'
      ]
    }
  },
  methods: {
    makePdf() {
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
          alert('اطلاعات شما ارسال شد')
        })
    }
  }
}
</script>

