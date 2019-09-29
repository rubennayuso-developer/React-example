import { mdiChevronDown } from '@mdi/js';
import Vuetify from 'vuetify/lib'
$font-prefix: "~@ibm/plex";
@import "~@ibm/plex/scss/ibm-plex.scss";
<style scoped>
    @import url("https://fonts.googleapis.com/css?family=IBM+Plex+Sans");
    .subPortion{
        margin: auto;
    }
   .nav {
        background: rgb(53, 96, 191);
        color: #ffffff;
    }

    .navHeading {
        padding: 20px;
        width: 350px;
        text-align: c;
        margin-left: 15%;
    }

    .navHeadingMobile {
        background: rgb(53, 96, 191);
        text-align: center;
        color: #ffffff;

    }

    .navLogo{
        width: 170px;
        position: absolute;
        height: auto;
        top: 40px;
        right: 15%;
    }

    .step{
        

        /* steps */

        font-family: IBM Plex Sans;
        font-style: normal;
        font-weight: 500;
        font-size: 15px;
        line-height: 19px;
        /* identical to box height */

        letter-spacing: 0.005em;

        /* Blue */

        color: #1977F3;
    }

    .heading1 {
        font-family: IBM Plex Sans;
        font-style: normal;
        font-weight: 500;
        font-size: 30px;
        line-height: 39px;
    }

    .paragraph {
        font-family: IBM Plex Sans;
        font-style: normal;
        font-weight: normal;
        font-size: 14px;
        line-height: 140%;
        /* or 20px */

        letter-spacing: 0.005em;
    }

    .vTabs {
        margin-top: 20px;
    }

    .vContainer {
        margin-top: 50px;
        padding-right: 25px !important;
        padding-left: 25px !important;
    }

    .textAreaContainer {
        height:140px;
        padding:0;
    }

    .checkbox {
        font-size: 12px;
        color: #333333;
    }

    .logoImage{
        width:100%;
    }

    .dropzoneContainer{
        height:230px;
        padding:0;
    }

    .subHeadingFormat{
        font-size: 1.5rem;
    }

    .unknown1{
        padding-top:5px;
    }

    .unknown2{
        padding:0;
        padding-top:10px;
        float: left;
        box-shadow: none !important;

           }

           .unknown2 div:nth-child(3) 
{
    display: none!important;
} 
.v-input__slot {
  box-shadow: none!important;
}

    .unknown3{
        padding-top:10px;
        padding-bottom:5px;
        font-size: 14px;
    }

    .unknown4{
        padding-top:5px;
        padding-bottom:10px;
        font-size: 14px;
    }

    .addFileButton{
        color:#4287f5;
    }

    .v-label {
        font-size: 12px;
        color: #333333;
    }

    .navHeading1 {
        font-size: 60px;
        font-family: IBM Plex Sans;
    }



    .navDescription {
        font-size: 16px;
        font-family: IBM Plex Sans;    
    }

    .context {
        
    }


</style>
    
<template>

    <v-App>
        <v-content class="context">
            <v-flex xs12 class="d-none d-sm-flex nav" >
                <div class="navHeading" >
                    <h1 class="navHeading1">Schema-fi</h1>
                    <div class="navDescriptions">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi tincidunt urna ex.</div>
                </div>
                <div class="navLogo">
                    <img src = "img.png" class="logoImage"></img>
                </div>
            </v-flex>
            <v-flex xs12 class="d-sm-none d-md-none navHeadingMobile">
                <div style="width: 100%;text-align: center;padding-left:50px;padding:20px;">
                    <h1>Schema-fi</h1>
                    <div>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi tincidunt urna ex.</div>
                </div>
            </v-flex>
            <v-container class="vContainer">
                <v-flex xs12 sm8 md6 justify-content text-left wrap class="subPortion">
                    <v-flex xs12 class="step"> 
                        Step 1
                    </v-flex>
                    <v-flex xs12 class="heading1">
                        Input CSV
                    </v-flex>
                    <v-flex xs12 class="paragraph">
                        Paste or upload your CSV file below. The first line of
                        your CSV must be column headers. If there are more than
                        two lines the additonal data will be ignored.
                    </v-flex>

                    <v-tabs 
                        class="vTabs"
                        v-model="tabs"
                        background-color="white"
                        color="blue" 
                        left
                    >
                        <v-tab>PASTE</v-tab>
                        <v-tab>UPLOAD</v-tab>

                        <v-tab-item :key="1">
                            <v-container fluid class="textAreaContainer">
                                <v-textarea
                                    name="input-7-1"
                                    label="Paste your files"
                                    value=""
                                    rows = "7"
                                    solo
                                    v-model="csvContext"
                                ></v-textarea>
                            </v-container>
                        </v-tab-item>
                        <v-tab-item :key="2">
                            <v-container fluid class="dropzoneContainer">
                                <vue2Dropzone id="upload" :options="config">
                                    <div class="dz-message">
                                        
                                        <h4 class="dropzone-custom-title mb-0 mt-3">Drag & Drop</h4>
                                        <div class="subtitle">or click to add your image</div>
                                    </div>
                                </vue2Dropzone>
                            </v-container>
                        </v-tab-item>
                    </v-tabs>
                    <v-flex xm12>
                        <v-checkbox
                            class="checkbox v-label"
                            v-model="TimescaleDB"
                            label="This is for a TimescaleDB Deployment"
                        ></v-checkbox>
                    </v-flex>
                    <v-flex xs12 sm4>
                        <v-btn color="blue" block  class="no-radius nextButton" @click="onClickStep1">Next</v-btn>
                    </v-flex>
                </v-flex>
            </v-container>

            <v-container class="vContainer">
                <v-flex xs12 sm8 md6 justify-content text-left wrap class="subPortion">
                    <v-flex xs12 class="step">
                        Step 2
                    </v-flex>
                    <v-flex xs12 class="heading1">
                        Format
                    </v-flex>
                    <v-flex xs12 class="paragraph">
                        Define the type of data in your CSV’s columns. Click
                        “generate code” when done.
                    </v-flex>
                    <v-flex xs12 v-if="steps > 1"> 
                    <v-flex xs12 class="unknown3">
                        Day of Week
                    <v-flex xs12 sm4 class="unknown1">
                        <v-autocomplete
                        v-model="e3"
                        color="blue"
                        :items="optionSelect"
                        class="forceBlue no-radius"
                        value="Date"
                        outlined
                        full-width
                        ></v-autocomplete>
                    </v-flex>
                    </v-flex>
                    <v-flex xs12 class="unknown4">
                        Steps Walked
                    <v-flex xs12 sm4 class="unknown1">
                        <v-autocomplete
                        v-model="e3"
                        color="blue"
                        :items="optionSelect"
                        outlined
                        class="forceBlue no-radius"
                        full-width
                        @click="onClick"
                        
                        ></v-autocomplete>
                    </v-flex>
                    </v-flex>
                    <v-flex xs12 sm4>
                        <v-btn color="blue" block class="no-radius generateButton" @click="onClickStep2">Generate code</v-btn>
                    </v-flex>
                    </v-flex>
                </v-flex>
            </v-container>
            <v-container class="vContainer">
                <v-flex xs12 sm8 md6 justify-content text-left wrap class="subPortion">
                    <v-flex xs12 class="step">
                        Step 3
                    </v-flex>
                    <v-flex xs12 class="heading1">
                        Copy Schema Code
                    </v-flex>
                    <v-flex xs12 class="paragraph">
                        Here’s your SQL schema. Copy and paste...
                    </v-flex>
                    <v-flex xs12 v-if="steps > 2">
                    <v-container fluid class="unknown2">
                        <v-textarea
                            name="input-7-1"
                            label=""
                            value=""
                            rows = "7"
                            solo
                            elevation="0"
                            v-model="csvContext"
                        ></v-textarea>
                    </v-container>
                    <v-flex xs12 sm4 class="unknown1">
                        <v-btn
                            color="blue " 
                            block
                            outlined
                            @click="onClickStep3"
                            class="no-radius button"
                        >Copy</v-btn>
                    </v-flex>
                    </v-flex>
                </v-flex>
            </v-container>
        </v-content>
    </v-App>
</template>

<script>
import vue2Dropzone from 'vue2-dropzone'
import 'vue2-dropzone/dist/vue2Dropzone.min.css'
export default {
    name: 'App',
    components: {
        vue2Dropzone
    },
    mounted () {
        window["controller"] = this;
    },
    methods: {
        setTextField(_text){
            this.csvContext = _text;
            this.tabs = 0;
        },
        onClickStep1(){
            this.steps = 2;
        },
        onClickStep2(){
            this.steps = 3;
        },
        onClickStep3(){
            alert("copy click");
        },
        onClick(){
            console.log(this);
            alert("hey");
        }
    },
    data: () => ({
        TimescaleDB: false,
        steps : 1,
        csvContext : "",
        tabs: 0,
        optionSelect: [
            "Deployment","Varchar","Boolean","Smallint","Integer","Decimal","Numeric","Real","Float","Double precision","Date","Time","Timestamp","Clob","Blob"
        ],
        config: {
            url: "https://your_url_uploadfile.com",
            acceptedFiles : "text/csv",
            dictDefaultMessage : "<img src='att.png' /><span style='color:#4287f5'>Add File</span> or drag & drop file here",
            accept: function(file, done) {
                var reader = new FileReader();
                reader.addEventListener("loadend", function(event) { 
                    console.log(event.target.result);
                    window["controller"].setTextField(event.target.result);
                });
                reader.readAsText(file);
                this.removeFile(file);
            }
        }
    })
};
</script>

<style>
* {
    margin: 0;
    padding: 0;
}
#app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
}
.w80 {
    width: 80%;
}
.w100 {
    width: 100%;
}
.w50 {
    width: 50%;
}
.m-center {
    margin: auto;
    padding: 50px;
}
.header {
    background: #4287f5 !important;
    color: #ffffff !important;
}
.title {
    padding: 20px;
    width: 50%;
    height: auto !important;
}
.titleL {
    font-size: 3rem !important;
    padding-bottom: 10px;
}
.titleN {
    font-size: 1rem !important;
    line-height: 1.25rem;
}
.forceBlue *{
    color: #4287f5 !important;
    border-color: #4287f5 !important;
    font-size: 14px;
    line-height: 18px;
}
.no-radius{
    border-radius: 0 !important;

}

.nextButton, button {
    width:150px !important;
    height: 42px !important;
    color: #ffffff !important;
}

.generateButton {
    background: #DFDFDF !important;
    
}
.container{
    padding: 0;
}
.v-menu__content{
    border: #4287f5 solid 1.5px;
}
.v-input--is-focused .v-input__slot{
    background: #4287f5 !important;
}
.v-input--is-focused *{
    color: #FFF !important;
}
.v-text-field__details{
    background: #FFF !important
}
.v-input__slot{
    margin-bottom: 0 !important;
}
</style>