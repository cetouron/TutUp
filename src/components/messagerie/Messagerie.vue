<template>
  <div class=" mt-6 container">
    <div class="messaging">
      <div class="inbox_msg">
        <div class="inbox_people">
          <div class="headind_srch">
            <div class="recent_heading">
              <h4>Recent</h4>
            </div>
            <div class="srch_bar">
              <div class="stylish-input-group">
                <input type="text" class="search-bar" placeholder="Search" />
                <span class="input-group-addon">
                  <button type="button">
                    <i class="fa fa-search" aria-hidden="true"></i>
                  </button>
                </span>
              </div>
            </div>
          </div>
          <div class="inbox_chat">
            <div class="chat_list active_chat">
              <div class="chat_people">
                <div class="chat_img">
                 
                 <v-avatar align="center">
                  <img src="../../assets/gerard.jpg" alt="sunil" />
                 </v-avatar>

                </div>
                <div class="chat_ib">
                  <h5>Gérard <span class="chat_date">12h</span></h5>
                  <div v-for="message in messages.slice(messages.length-1,messages.length)"
                    :key="message.m">
                    <p>
                    {{message.m}}
                  </p>
                  </div>
                </div>
              </div>
            </div>
            <div class="chat_list">
              <div class="chat_people">
                <div class="chat_img">
                <v-avatar align="center">
                  <img
                    src="https://st2.depositphotos.com/1005637/6441/i/600/depositphotos_64412309-stock-photo-friendly-middle-aged-woman.jpg"
                    alt="sunil"
                  />
                   </v-avatar>
                </div>
                <div class="chat_ib">
                  <h5>Noémie<span class="chat_date">20 dec. 20</span></h5>
                  <p>
                    Bonnes fêtes.
                  </p>
                </div>
              </div>
            </div>
            <div class="chat_list">
              <div class="chat_people">
                <div class="chat_img">
                                  <v-avatar align="center">
 
                  <img
                    src="https://img.freepik.com/photos-gratuite/portrait-homme-adulte-se-prepare-exercice_23-2148531067.jpg?size=338&ext=jpg"
                    alt="sunil"
                  />
                   </v-avatar>
                </div>
                <div class="chat_ib">
                  <h5>Adrien<span class="chat_date">4 oct. 20</span></h5>
                  <p>
                    Merci à vous !
                  </p>
                </div>
              </div>
            </div>
          </div>
        </div>
        <div class="mesgs">
          <div class="msg_history">
            <div
              class="incoming_msg"
              v-for="message in messages"
              :key="message.m"
            >
            <div v-if="message.align=='right'">
              <div class="received_msg" align="right">
                <div class="received_withd_msg" >
                  <p>
                   

                    {{ message.m }}
                  </p>
                  <span class="time_date"> {{ message.h }} | {{ message.d }}</span>
                </div>
              </div>
            </div>

            <div v-else>
              <div class="received_msg" align="left">
                <div class="received_withd_msg" >
                  <p>

                    <v-row>
                      <v-col  cols="2">
                    <v-avatar align="center">
                  <img 
                      height="40" src="../../assets/gerard.jpg" />
                 </v-avatar>
                      </v-col>
                    <v-col cols="10">
                    {{ message.m }}
                    </v-col>
                    </v-row>
                  </p>
                  <span class="time_date"> {{ message.h }} | {{ message.d }}</span>
                </div>
              </div>
            </div>
            </div>
          </div>
          <div class="type_msg">
            <div class="input_msg_write">
              <input
                @keyup.enter="addMovie"
                v-model="message"
                type="text"
                class="write_msg"
                placeholder="Type a message"
              />
              <button class="msg_send_btn" type="button" v-on:click="addMovie">
                <i class="fa fa-paper-plane-o" aria-hidden="true"></i>
              </button>
            </div>
          </div> 
        </div> 
      </div>
    </div>
  </div>
</template>


<script>
export default {
  name: "PrivateChat",
  data() {
    return {
      message: null,
      messages: [ 
        {m:"Bonjour jeune homme, je viens vers vous dans le cadre du tutorat", h:'23:37' , d:'24 Janvier', align:"left"},
        {m:"Bonjour Monsieur", h:'11:01' , d:'25 Janvier', align:"right"},
        {m:"De quoi s'agit-il ?", h:'11:02' , d:'25 Janvier', align:"right"},
        {m:"Mon souhait est d'avoir des cours pour mon fils Loïc en Français", h:'13:21' , d:'Janvier 25', align:"left"},
        {m:"Evidement, on se donne rendez-vous quand ?", h:'20:53' , d:'25 Janvier', align:"right"},
        {m:"Je pense qu'on peut faire ça lundi prochain à 17h30 ?", h:'00:26' , d:'26 Janvier', align:"left"},
        {m:"J'habite rue des Girouettes", h:'00:32' , d:'26 Janvier', align:"left"},
        ]
    };
  },
  methods: {
    addMovie() {
     this.messages.push({m:this.message, align:"right", h:"A l'instant" , d:"Aujourd'hui"},);
      this.message = null; 
    },

    saveMessage() {
      //save to firestore
    /*  db.collection("chat").add({
        message: this.message
      });
      this.message = null;*/
    },
    fetchMessages() {
    /*  db.collection("chat")
        .get()
        .then(querySnapShot => {
          let allMessages = [];
          querySnapShot.forEach(doc => {
            allMessages.push(doc.data());
          });
          this.messages = allMessages;
        });*/
    }
  },
  created() {
    this.fetchMessages;
  }
};
</script>

<style scoped>
.container {
  max-width: 1170px;
  margin: auto;
}
img {
  max-width: 100%;
}
.inbox_people {
  background: #f8f8f8 none repeat scroll 0 0;
  float: left;
  overflow: hidden;
  width: 40%;
  border-right: 1px solid #c4c4c4;
}
.inbox_msg {
  border: 1px solid #c4c4c4;
  clear: both;
  overflow: hidden;
}
.top_spac {
  margin: 20px 0 0;
}

.recent_heading {
  float: left;
  width: 40%;
}
.srch_bar {
  display: inline-block;
  text-align: right;
  width: 60%;
}
.headind_srch {
  padding: 10px 29px 10px 20px;
  overflow: hidden;
  border-bottom: 1px solid #c4c4c4;
}

.recent_heading h4 {
  color: #33637a;
  font-size: 21px;
  margin: auto;
}
.srch_bar input {
  border: 1px solid #cdcdcd;
  border-width: 0 0 1px 0;
  width: 80%;
  padding: 2px 0 4px 6px;
  background: none;
}
.srch_bar .input-group-addon button {
  background: rgba(0, 0, 0, 0) none repeat scroll 0 0;
  border: medium none;
  padding: 0;
  color: #707070;
  font-size: 18px;
}
.srch_bar .input-group-addon {
  margin: 0 0 0 -27px;
}

.chat_ib h5 {
  font-size: 15px;
  color: #464646;
  margin: 0 0 8px 0;
}
.chat_ib h5 span {
  font-size: 13px;
  float: right;
}
.chat_ib p {
  font-size: 14px;
  color: #989898;
  margin: auto;
}
.chat_img {
  float: left;
  width: 11%;
}
.chat_ib {
  float: left;
  padding: 0 0 0 15px;
  width: 88%;
}

.chat_people {
  overflow: hidden;
  clear: both;
}
.chat_list {
  border-bottom: 1px solid #c4c4c4;
  margin: 0;
  padding: 18px 16px 10px;
}
.inbox_chat {
  height: 550px;
  overflow-y: scroll;
}

.active_chat {
  background: #ebebeb;
}

.incoming_msg_img {
  display: inline-block;
  width: 6%;
}
.received_msg {
  display: inline-block;
  padding: 0 0 0 10px;
  vertical-align: top;
  width: 92%;
}
.received_withd_msg p {
  background: #ebebeb none repeat scroll 0 0;
  border-radius: 3px;
  color: #646464;
  font-size: 14px;
  margin: 0;
  padding: 5px 10px 5px 12px;
  width: 100%;
}
.time_date {
  color: #747474;
  display: block;
  font-size: 12px;
  margin: 8px 0 0;
}
.received_withd_msg {
  width: 57%;
}
.mesgs {
  float: left;
  padding: 30px 15px 0 25px;
  width: 60%;
}

.sent_msg p {
  background: #fa580d none repeat scroll 0 0;
  border-radius: 3px;
  font-size: 14px;
  margin: 0;
  color: #fff;
  padding: 5px 10px 5px 12px;
  width: 100%;
}
.outgoing_msg {
  overflow: hidden;
  margin: 26px 0 26px;
}
.sent_msg {
  float: right;
  width: 46%;
}
.input_msg_write input {
  background: rgba(0, 0, 0, 0) none repeat scroll 0 0;
  border: medium none;
  color: #4c4c4c;
  font-size: 15px;
  min-height: 48px;
  width: 100%;
}

.type_msg {
  border-top: 1px solid #c4c4c4;
  position: relative;
}
.msg_send_btn {
  background: #05728f none repeat scroll 0 0;
  border: medium none;
  border-radius: 50%;
  color: #fff;
  cursor: pointer;
  font-size: 17px;
  height: 33px;
  position: absolute;
  right: 0;
  top: 11px;
  width: 33px;
}
.messaging {
  padding: 0 0 50px 0;
}
.msg_history {
  height: 516px;
  overflow-y: auto;
}
</style>
