<template>


<div>

  <header class="lightgreentop">
      <div id="navbarHeader" class="collapse bg-dark">

      </div>
        <div class="container">
           <div class="row">
              <div class="col-md-2 midhead">
                  <a href="#" class="navbar-brand d-flex">
                  <img class="me-3" src="https://ktu.edu/wp-content/uploads/2016/08/logo_ukrainos_veliava.svg" alt="" width="110px">
                  </a>
              </div>
              <div class="col-md-7 midhead3">
                <h1 class="mainf">ACADEMIC INFORMATION SYSTEM</h1>
              </div>
              <div class="col-md-3">
                <nav>
        <div class="dropdown midhead2">

  <button class="dropdown-toggle buttonktu" type="button" id="dropdownMenuButton1" data-bs-toggle="dropdown" aria-expanded="false">
    my KTU
  </button>

  <ul class="dropdown-menu" aria-labelledby="dropdownMenuButton1">
   <li class="menu-item menu-item-type-custom menu-item-object-custom menu-item-2131 rect-button">
     <a class="topmenu mainf" title="MOODLE aplinka" target="_blank" href="https://moodle.ktu.edu/?lang=en">MOODLE</a></li>

	<li class="menu-item">
    <a class="topmenu mainf" title="akademinÄ— sistema (AIS)" target="_blank" href="https://uais.cr.ktu.lt/ktuis/stp_prisijungimas?p_lang=LTU">academic IS</a></li>

	<li class="menu-item">
    <a class="topmenu mainf" title="office365 aplinka" target="_blank" href="https://live.ktu.lt">Office365</a></li>

	<li class="menu-item">
    <a class="topmenu mainf" title="intranetas &#8211; prisijungimas per KTU VPN" target="_blank" href="https://intranet.ktu.lt"><span class="glyphicon intranetas &#8211; prisijungimas per KTU VPN"></span>&nbsp;intranet</a></li>

	<li class="menu-item"><a class="topmenu mainf" title="darbuotojÅ³ paÅtas" target="_blank" href="https://pastas.ktu.lt">email for employees</a></li>
	<li class="menu-item"><a class="topmenu mainf" title="darbuotojo atmintinÄ—" target="_blank" href="https://en.ktu.edu/employee-guide/">employee guide</a></li>
	<li class="menu-item"><a class="topmenu mainf" title="praneÅk" target="_blank" href="https://pranesk.ktu.edu/en">report</a></li>
	<li class="menu-item"><a class="topmenu mainf" title="pagalba" target="_blank" href="https://help.ktu.edu/?lang=en">help</a></li>
</ul>
</div>
                </nav>
              </div>
            </div>

        </div>
    </header>

<main class="_home d-flex justify-content-centr">
      <section class="text-center container">
        <div class="row py-lg-5">
          <div class="col-lg-4 col-md-6 mx-auto mainf">

            <h2 class="">
              Thanks, you just
            </h2>
            <h2 class="fw-bold mb-2 pad">
              presented credentials.
            </h2>
            <div class="accordion my-2" id="accordion1" v-for="data in result.vp_token.verifiableCredential" v-bind:key="data.id">
              <div class="accordion-item" style="border:none;">
                <h2 class="accordion-header" :id="'heading'+result.vp_token.verifiableCredential.indexOf(data)">
                  <button class="accordion-button collapsed border1" type="button" data-bs-toggle="collapse" :data-bs-target="'#collapse'+result.vp_token.verifiableCredential.indexOf(data)" aria-expanded="false" :aria-controls="'collapse'+result.vp_token.verifiableCredential.indexOf(data)">
                     <i class="bi bi-check-circle-fill text-primary me-2"></i>
                    {{data.type[data.type.length-1]}}
                  </button>
                </h2>
                <div :id="'collapse'+result.vp_token.verifiableCredential.indexOf(data)" class="accordion-collapse collapse border2" :aria-labelledby="'heading'+result.vp_token.verifiableCredential.indexOf(data)" data-bs-parent="#accordionExample">
                  <div class="accordion-body text-start">
                    <!-- VerifiableId -->
                    <div v-if="data.type[data.type.length-1] == 'VerifiableId'">
                      <span>
                        <i class="bi bi-check"></i>
                        Family Name: {{data.credentialSubject.familyName}}
                      </span>
                      <br>
                      <span>
                        <i class="bi bi-check"></i>
                        First Name: {{data.credentialSubject.firstName}}
                      </span>
                      <br>
                      <span>
                        <i class="bi bi-check"></i>
                         Date Of Birth: {{data.credentialSubject.dateOfBirth}}
                      </span>
                      <br>
                      <span>
                        <i class="bi bi-check"></i>
                        Personal Identifier: {{data.credentialSubject.personalIdentifier}}
                      </span>
                      <br>
                      <span>
                        <i class="bi bi-check"></i>
                        Name At Birth: {{data.credentialSubject.nameAndFamilyNameAtBirth}}
                      </span>
                      <br>
                      <span>
                        <i class="bi bi-check"></i>
                        Place Of Birth: {{data.credentialSubject.placeOfBirth}}
                      </span>
                      <br>
                      <span>
                        <i class="bi bi-check"></i>
                        Current Address: {{data.credentialSubject.currentAddress}}
                      </span>
                      <br>
                      <span>
                        <i class="bi bi-check"></i>
                        Gender: {{data.credentialSubject.gender}}
                      </span>
                    </div>

                    <!-- EuropeanBankIdentity -->
                    <div v-if="data.type[data.type.length-1] == 'EuropeanBankIdentity'">
                      <span>
                        <i class="bi bi-check"></i>
                        ID: {{data.credentialSubject.id}}
                      </span>
                      <br>
                      <span>
                        <i class="bi bi-check"></i>
                        Family name: {{data.credentialSubject.familyName}}
                      </span>
                      <br>
                      <span>
                        <i class="bi bi-check"></i>
                         Given names: {{data.credentialSubject.givenName}}
                      </span>
                      <br>
                      <span>
                        <i class="bi bi-check"></i>
                        Date of birth: {{data.credentialSubject.birthDate}}
                      </span>
                      <br>
                      <span>
                        <i class="bi bi-check"></i>
                        Country of birth: {{data.credentialSubject.placeOfBirth.country}}
                      </span>
                      <br>
                      <span>
                        <i class="bi bi-check"></i>
                        Locality of birth: {{data.credentialSubject.placeOfBirth.locality}}
                      </span>
                    </div>

                    <!-- VerifiableDiploma -->

                     <div v-if="data.type[data.type.length-1] == 'VerifiableDiploma'">
                      <span>
                        <i class="bi bi-check"></i>
                        ID: {{data.credentialSubject.id}}
                      </span>
                      <br>
                      <span>
                        <i class="bi bi-check"></i>
                        Family name: {{data.credentialSubject.familyName}}
                      </span>
                      <br>
                      <span>
                        <i class="bi bi-check"></i>
                         Given names: {{data.credentialSubject.givenName}}
                      </span>
                      <br>
                      <span>
                        <i class="bi bi-check"></i>
                        Date of birth: {{data.credentialSubject.dateOfBirth}}
                      </span>
                      <br>
                      <span>
                        <i class="bi bi-check"></i>
                        Education Name: {{data.credentialSubject.identifier}}
                      </span>
                      <br>

                    </div>

                  </div>
                </div>
              </div>
            </div>
            <div v-if="result.verification_result.valid" class="alert alert-success mt-4 table1" role="alert">
              <strong>The verification was successful</strong>
              <br>
              Verification Policies
              <br>
              {{JSON.stringify(result.verification_result.policyResults, undefined, 2)}}
            </div>
            <div v-else class="alert alert-danger mt-4" role="alert">
              <strong>The verification failed</strong>
              <br>
              Verification Policies
              <br>
              {{JSON.stringify(result.verification_result.policyResults, undefined, 2)}}
            </div>
            <div v-if="result.verification_result.valid" class="alert alert-secondary mt-4" role="alert">
              Authenticated session established
              <br>
              <span>
                <i class="bi bi-dot"></i>
                <a href="#" v-if="authenticatedDID === 'View authenticated DID'" class="text-dark" @click="viewAuthenticatedDID">View authenticated DID</a>
                <a href="#" v-else class="text-dark" @click="viewAuthenticatedDID">{{authenticatedDID.slice(0,30)}}...</a>
              </span>
              <br>
              <span>
                <i class="bi bi-dot"></i>
                <a href="#" v-if="access_token === 'View session token'" class="text-dark" @click="viewSessionToken">View session token</a>
                <a href="#" v-else class="text-dark" @click="viewSessionToken">{{access_token.slice(0,30)}}...</a>
              </span>
            </div>
            <div v-else class="alert alert-secondary mt-4" role="alert">
              No authenticated session established!
              <br>
              <span>
                <i class="bi bi-dot"></i>
                <a href="#" class="text-dark" @click="viewAuthenticatedDID">No authenticated DID</a>
              </span>
              <br>
              <span>
                <i class="bi bi-dot"></i>
                <a href="#" class="text-dark" @click="viewSessionToken">No session token</a>
              </span>
            </div>
          </div>
        </div>
      </section>

    </main>


<footer>
    <div class="container" style="padding-bottom: 10px;">
        <div class="row">
            <div class="col-md-12">
                <div class="footer-border"></div>
            </div>
        </div>
    </div>

    <div class="container">
        <div class="row">
            <div class="col-md-5" id="icons">
               <p><strong>Kaunas University of Technology</strong> įm. k. 111950581<br />
               company code 111950581, VAT code LT119505811<br />
address K. Donelaičio St. 73, 44249 Kaunas, Lithuania<br />
+370 (37) 300 000, 300 421, fax +370 (37) 324 144<br />
email <a href="mailto:ktu@ktu.lt">ktu@ktu.lt</a></p>
                      <div class="social-icons">
                      <a href="https://www.facebook.com/ktu.lt" target="_blank"><img src="https://ktu.edu/wp-content/themes/ktu/images/social/Social_media-facebook.svg" alt="Facebook" title="Facebook"></a>
                      <a href="https://www.linkedin.com/company/ktu" target="_blank"><img src="https://ktu.edu/wp-content/themes/ktu/images/social/Social_media-linkedin.svg" alt="Linkedin" title="Linkedin"></a>
                      <a href="https://www.youtube.com/user/ktuvideo" target="_blank"><img src="https://ktu.edu/wp-content/themes/ktu/images/social/Social_media-youtube.svg" alt="YouTube" title="YouTube"></a>
                      <a href="https://www.instagram.com/ktuspace/" target="_blank"><img src="https://ktu.edu/wp-content/themes/ktu/images/social/Social_media-instagram.svg" alt="Instagram" title="Instagram"></a>
                    </div>
              </div>

            <div class="col-md-2">
              <div class="menufooter">


                <div class="dropdown">
  <a class="dropdown-toggle buttonktu" id="buttonfooter2" href="#" role="button" data-bs-toggle="dropdown" aria-expanded="false">
    Quick Links
  </a>

  <ul class="dropdown-menu" aria-labelledby="dropdownMenuLink">
    <li class="footerli"><a class="downmenu mainf" title="COVID-19" href="https://en.ktu.edu/covid-19/">COVID-19</a></li>
	                    <li class="footerli"><a class="downmenu mainf" title="Bendrabučiai" target="_blank" href="https://dormitory.ktu.edu">Dormitories</a></li>

                      <li class="footerli"><a class="downmenu mainf" title="Akademiniai mainai" href="https://en.ktu.edu/erasmus/">Academic exchange</a></li>
	                    <li class="footerli"><a class="downmenu mainf" title="Darbas KTU" href="https://en.ktu.edu/work-at-ktu/">Work at KTU</a></li>
	                    <li class="footerli"><a class="downmenu mainf" title="Dokumentai" href="https://en.ktu.edu/documents/">Documents</a></li>
	                    <li class="footerli"><a class="downmenu mainf" title="Kontaktai" href="https://en.ktu.edu/contacts/">Contacts</a></li>
	                    <li class="footerli"><a class="downmenu mainf" title="KTU virtualus turas" target="_blank" href="https://tour.ktu.edu/#EN">Virtual KTU tour</a></li>
  </ul>
  </div></div>

</div>
<div class="col-md-2">
  <a class="dropdown-toggle buttonktu" id="buttonfooter2" href="#" role="button" data-bs-toggle="dropdown" aria-expanded="false">
   Privacy
  </a>

  <ul class="dropdown-menu" aria-labelledby="dropdownMenuLink">
    <li class="footerli"><a class="downmenu mainf" title="Privacy" href="https://en.ktu.edu/privacy/">Privacy</a></li>
    <li class="footerli"><a class="downmenu mainf" title="Cookies" href="https://en.ktu.edu/privacy/cookies/">Cookies</a></li>
  </ul>
    </div>
<div class="col-md-3">
  <a class="buttonktu" id="buttonfooter2" href="https://en.ktu.edu/media-enquiries/" role="button" aria-expanded="false">
   For media enquiries
  </a>
</div>
        </div>
</div>




</footer>
    <!-- <main class="_home d-flex justify-content-centr align-items-center">
      <section class="py-5 text-center container">
        <div class="row py-lg-5">
          <div class="col-lg-4 col-md-6 mx-auto">
            <img src="/favicon.png"/>
            <h2 class="fw-normal">
              Thanks, you just
            </h2>
            <h2 class="fw-bold mb-2">
              presented credentials.
            </h2>
            <div class="accordion my-2" id="accordion1" v-for="data in result.vp_token.verifiableCredential" v-bind:key="data.id">
              <div class="accordion-item">
                <h2 class="accordion-header" :id="'heading'+result.vp_token.verifiableCredential.indexOf(data)">
                  <button class="accordion-button collapsed" type="button" data-bs-toggle="collapse" :data-bs-target="'#collapse'+result.vp_token.verifiableCredential.indexOf(data)" aria-expanded="false" :aria-controls="'collapse'+result.vp_token.verifiableCredential.indexOf(data)">
                     <i class="bi bi-check-circle-fill text-primary me-2"></i>
                    {{data.type[data.type.length-1]}}
                  </button>
                </h2>
                <div :id="'collapse'+result.vp_token.verifiableCredential.indexOf(data)" class="accordion-collapse collapse" :aria-labelledby="'heading'+result.vp_token.verifiableCredential.indexOf(data)" data-bs-parent="#accordionExample">
                  <div class="accordion-body text-start">
                   VerifiableId
                    <div v-if="data.type[data.type.length-1] == 'VerifiableId'">
                      <span>
                        <i class="bi bi-check"></i>
                        Family Name: {{data.credentialSubject.familyName}}
                      </span>
                      <br>
                      <span>
                        <i class="bi bi-check"></i>
                        First Name: {{data.credentialSubject.firstName}}
                      </span>
                      <br>
                      <span>
                        <i class="bi bi-check"></i>
                         Date Of Birth: {{data.credentialSubject.dateOfBirth}}
                      </span>
                      <br>
                      <span>
                        <i class="bi bi-check"></i>
                        Personal Identifier: {{data.credentialSubject.personalIdentifier}}
                      </span>
                      <br>
                      <span>
                        <i class="bi bi-check"></i>
                        Name At Birth: {{data.credentialSubject.nameAndFamilyNameAtBirth}}
                      </span>
                      <br>
                      <span>
                        <i class="bi bi-check"></i>
                        Place Of Birth: {{data.credentialSubject.placeOfBirth}}
                      </span>
                      <br>
                      <span>
                        <i class="bi bi-check"></i>
                        Current Address: {{data.credentialSubject.currentAddress}}
                      </span>
                      <br>
                      <span>
                        <i class="bi bi-check"></i>
                        Gender: {{data.credentialSubject.gender}}
                      </span>
                    </div>

                     EuropeanBankIdentity
                    <div v-if="data.type[data.type.length-1] == 'EuropeanBankIdentity'">
                      <span>
                        <i class="bi bi-check"></i>
                        ID: {{data.credentialSubject.id}}
                      </span>
                      <br>
                      <span>
                        <i class="bi bi-check"></i>
                        Family name: {{data.credentialSubject.familyName}}
                      </span>
                      <br>
                      <span>
                        <i class="bi bi-check"></i>
                         Given names: {{data.credentialSubject.givenName}}
                      </span>
                      <br>
                      <span>
                        <i class="bi bi-check"></i>
                        Date of birth: {{data.credentialSubject.birthDate}}
                      </span>
                      <br>
                      <span>
                        <i class="bi bi-check"></i>
                        Country of birth: {{data.credentialSubject.placeOfBirth.country}}
                      </span>
                      <br>
                      <span>
                        <i class="bi bi-check"></i>
                        Locality of birth: {{data.credentialSubject.placeOfBirth.locality}}
                      </span>
                    </div>

                  </div>
                </div>
              </div>
            </div>
            <div v-if="result.verification_result.valid" class="alert alert-success mt-4" role="alert">
              <strong>The verification was successful</strong>
              <br>
              Verification Policies
              <br>
              {{JSON.stringify(result.verification_result.policyResults, undefined, 2)}}
            </div>
            <div v-else class="alert alert-danger mt-4" role="alert">
              <strong>The verification failed</strong>
              <br>
              Verification Policies
              <br>
              {{JSON.stringify(result.verification_result.policyResults, undefined, 2)}}
            </div>
            <div v-if="result.verification_result.valid" class="alert alert-secondary mt-4" role="alert">
              Authenticated session established
              <br>
              <span>
                <i class="bi bi-dot"></i>
                <a href="#" v-if="authenticatedDID === 'View authenticated DID'" class="text-dark" @click="viewAuthenticatedDID">View authenticated DID</a>
                <a href="#" v-else class="text-dark" @click="viewAuthenticatedDID">{{authenticatedDID.slice(0,30)}}...</a>
              </span>
              <br>
              <span>
                <i class="bi bi-dot"></i>
                <a href="#" v-if="access_token === 'View session token'" class="text-dark" @click="viewSessionToken">View session token</a>
                <a href="#" v-else class="text-dark" @click="viewSessionToken">{{access_token.slice(0,30)}}...</a>
              </span>
            </div>
            <div v-else class="alert alert-secondary mt-4" role="alert">
              No authenticated session established!
              <br>
              <span>
                <i class="bi bi-dot"></i>
                <a href="#" class="text-dark" @click="viewAuthenticatedDID">No authenticated DID</a>
              </span>
              <br>
              <span>
                <i class="bi bi-dot"></i>
                <a href="#" class="text-dark" @click="viewSessionToken">No session token</a>
              </span>
            </div>
            <p class="text-muted fw-bold mt-5">© 2022 walt.id</p>
          </div>
        </div>
      </section>
    </main> -->



  </div>
</template>


<script>
if (window.opener != null) {
  window.opener.location = window.location
  window.close()
}
export default {
  name: 'success.vue',
  data (){
    return{
      access_token:  'View session token',
      authenticatedDID: 'View authenticated DID'
    }
  },
  async asyncData ({ $axios, route }) {
    console.log(route.query.access_token)
    let result = {}
    let protectedData = {}
    if (route.query.access_token != null) {
      await $axios.get('/verifier-api/auth?access_token=' + route.query.access_token)
        .then((response) => {
          result = response.data
          console.log(response.data)
          return $axios.get('/verifier-api/protected', {
            headers: {
              Authorization: 'Bearer ' + result.auth_token
            }
          })
        })
        .then((dataResponse) => {
          protectedData = dataResponse.data
        })
        .catch((error) => {
          console.log(error)
        })
    }
    return { result, protectedData }
  },
  methods:{
    viewSessionToken (){
      this.access_token = this.result.auth_token;
    },
    viewAuthenticatedDID(){
      this.authenticatedDID = this.result.subject
    }
  }
}
</script>

<style scoped>
@import url("https://fonts.cdnfonts.com/css/pf-dintext-pro-medium");
main{
  padding-bottom: 10px;
}
.dropdown-menu{
  margin: 0px;
    padding: 0px;
    border: 0px;
    background-color: rgb(243, 242, 238);

    box-shadow: 0px 0px 0px 0px;
    border-radius: 0px;

}
.downmenu{


    padding: 10px 15px 10px 15px;
    display: block;
    color: black;
    background-color: transparent;
    transition: all 0.25s ease-in-out;
}
.footerli{
     width: 100%;
    padding: 0 20px;
    font-family: "PF DinText Pro Medium", sans-serif;
    color: black;
    font-size: 16px;
    line-height: 35px;
    display: block;
    background-color: #f3f2ee;

}
.footerli:hover{
  background-color: rgb(252, 251, 248);
}
#buttonfooter1{
  margin-left: 100px;
      background-color: #f3f2ee;
    border-radius: 3px;
    border-color: #f3f2ee;
    color: black;
    font-size: 16px;
    font-weight: 500;
    padding: 10px 20px;
    text-decoration: none;
    display: block;
    font-family: "PF DinText Pro Medium", sans-serif;
    width: 205px;
}
#buttonfooter2{
      margin-left: 100px;
      background-color: #f3f2ee;
    border-radius: 3px;
    border-color: #f3f2ee;
    color: black;
    font-size: 16px;
    font-weight: 500;
    padding: 10px 20px;
    text-decoration: none;
    display: block;
    font-family: "PF DinText Pro Medium", sans-serif;
    width: 100%;
}
#icons{
    position: relative;
    min-height: 1px;
    padding-right: 15px;
    padding-left: 15px;
}
footer{
  padding: 0;
    padding-bottom: 10px;
    width: 100%;
    float: left;
    display: block;
}
.container{
  width: 1170px;
  padding-right: 15px;
  padding-left: 15px;
  margin-right: auto;
  margin-left: auto;
}
.social-icons img {
    width: 24px;
}
.social-icons{
    position: absolute;
    top: 30px;
    right: 0;
    transform: translate(80%, 0);
     z-index: 20;
}
.social-icons{
  display: block;
  height: auto;
  max-width: 100%;
  border: 0;
}
.social-icons:hover{
  display: block;
  height: auto;
  max-width: 100%;
  border: 0;
}

.dropdown-menu{
       background: transparent;
       border:none;
}
.topmenu:hover {
  background-color: #000000; /* Green */
  color: white;
  transition-duration: 0.5s;
   text-decoration: none;
}
.topmenu{
  border-radius: 3px;
    border-top-left-radius: 3px;
    border-top-right-radius: 3px;
    border-bottom-right-radius: 3px;
    border-bottom-left-radius: 3px;
    margin-top: 1px;

        padding: 10px 15px 10px 15px;
    display: block;
    color: black;
    background: #fff;
    border: 1px solid;
        white-space: initial;
            clear: both;
    font-weight: normal;
    line-height: 1.42857143;
    text-decoration: none;
}
.mainf{
  font-family: "PF DinText Pro Medium", sans-serif;
  font-weight: normal;
  letter-spacing: 0.5px;
}
.labelfon{
  font-weight: 10;
}
.buttonktu:hover, .buttonktu:focus {
  background-color: #000000; /* Green */
  color: white;
  transition-duration: 0.5s;
}
.buttonktu{
      position: relative;
    background: transparent;
    float: none !important;

    bottom: initial;
    right: initial;
    width: 120px;
    height: 50px;
    border-radius: 4px;

    font-size: 16px !important;
    padding: 8px 20px 8px 19px;
    border: 2px solid #000101;
    text-align: center;
    color: #000101;
    letter-spacing: 0.5px;
    box-shadow: none;
    font-family: "PF DinText Pro Medium";

}
.lightgreentop{
      background: #e1f1ec;
}
.midhead{
  display: flex;
  justify-content: center;
  align-items: center;
}
.midhead2{
  height: 120px;
  display: flex;
  justify-content: center;
  align-items: center;
}
.midhead3{
  height: 120px;
  display: flex;
  justify-content: center;
  align-items: center;
}
.mainktufont{
      color: #000101;
    font-family: "PF DinText Pro Medium";
    font-size: 36px;
    font-weight: 500;
    line-height: 24px;
    margin-bottom: 20px;
}
label{
  font-size: 20px;
  margin-top: -3px;
  font-weight: 600;
}

.accordion-button:not(.collapsed) {
    color: #000000;
    background-color: #ffffff;
}
.table1{
  background: #e1f1ec;
}
.border1:hover{
  background-color: #000000; /* Green */
  color: white;
  transition-duration: 0.5s;
}
.border1{
  border-radius: 4px;
  border: 2px solid black;
  box-shadow: none;
}
.border2{
  border-radius: 4px;
  border: 2px solid black;
  box-shadow: none;
  border-top:none;
}
.pad{
  padding-bottom: 20px;
}
._home {
  padding-top: 110px;
  padding-bottom: 110px;
}
._btn {
  font-size: 18px;
  padding: 10px 55px;
}
._btnVerif {
  font-size: 18px;
  padding: 5px 55px;
  width: 360px;
  height: 60px;
}
</style>
