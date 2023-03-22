<template>
  <header></header>
  <div id="app" class="flex justify-center  items-center min-h-screen sm:-mx-6 lg:-mx-8  ">
    <div class="flex flex-col">
      <div class="">
        <div class="inline-block min-w-full py-2 sm:px-6 lg:px-8">
          <div class="overflow-hidden">

            <table class="min-w-full text-center min-[320px]:text-center max-[600px]:text-xs text-sm font-light overflow-x-auto">
              <thead class="border-b font-medium dark:border-neutral-500">
                <tr>
                  <th scope="col" class="min-[320px]:text-center max-[600px]:px-1 px-6 py-2 min-[320px]:text-center max-[600px]:hidden">#</th>
                  <th scope="col" class="min-[320px]:text-center max-[600px]:px-1 px-6 py-2">Masjid</th>
                  <th scope="col" class="min-[320px]:text-center max-[600px]:px-1 px-6 py-2">Keunggulan</th>
                  <th scope="col" class="min-[320px]:text-center max-[600px]:px-1 px-6 py-2 ">#</th>
                </tr>
              </thead>
              <tbody>
                <tr class="border-b dark:border-neutral-500" v-for="message in messages">
                  <td class="whitespace-nowrap min-[320px]:px-2 max-[600px]:px-2 px-6 min-[320px]:text-center max-[600px]:hidden py-2 font-medium">*</td>
                  <td class="whitespace-nowrap min-[320px]:px-2 max-[600px]:px-2 px-6 py-2 font-medium"> {{ message.name }}</td>
                  <td class="whitespace-nowrap min-[320px]:px-2 max-[600px]:px-2 px-6 py-2 font-medium">{{ message.takjil }}</td>
                  <td class="whitespace-nowrap min-[320px]:px-2 max-[600px]:px-2 px-6 py-2 font-medium"><button @click="deleteMessage(message.id)" class=" min-[320px]:text-center max-[600px]:p-1 p-2.5 bg-red-400 rounded-xl hover:rounded-3xl hover:bg-red-700 transition-all duration-300 text-black inline-block">
                        <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-4 h-4">
                        <path stroke-linecap="round" stroke-linejoin="round" d="M14.74 9l-.346 9m-4.788 0L9.26 9m9.968-3.21c.342.052.682.107 1.022.166m-1.022-.165L18.16 19.673a2.25 2.25 0 01-2.244 2.077H8.084a2.25 2.25 0 01-2.244-2.077L4.772 5.79m14.456 0a48.108 48.108 0 00-3.478-.397m-12 .562c.34-.059.68-.114 1.022-.165m0 0a48.11 48.11 0 013.478-.397m7.5 0v-.916c0-1.18-.91-2.164-2.09-2.201a51.964 51.964 0 00-3.32 0c-1.18.037-2.09 1.022-2.09 2.201v.916m7.5 0a48.667 48.667 0 00-7.5 0" />
                        </svg>
                        </button>
                  </td>
              
                </tr>
                
              </tbody>
              <br>
              
            </table>
            <div class="flex flex-col min-[320px]:justify-center max-[600px]:ml-2 text-black text-sm  font-medium w-full">
                <label for="tambah" class="min-[320px]:text-black max-[600px]:text-xs mb-1"> Tambah data</label>
              <button @click="layout = 'grid'" id="tambah" class="mr-4 p-2.5 w-8 min-[320px]:text-center max-[600px]:w-8 bg-green-400 rounded-xl hover:rounded-3xl hover:bg-green-700 transition-all duration-300 text-black flex justify-center">
                <svg xmlns="http://www.w3.org/2000/svg" width="12" height="12" viewBox="0 0 24 24"><path d="M24 10h-10v-10h-4v10h-10v4h10v10h4v-10h10z"/></svg>
                        </button>
              </div>
            <br>
            <br>
            
          </div>
          <div v-if="layout == 'grid'" autocomplete="off" class="ml-2">
            <div class="relative z-0 mb-6">
              <input autocomplete="off"
              ref="name"
                type="text"
                id="nama"
                class="min-[320px]:text-xs max-[600px]:text-xs block py-2.5 px-0 w-full text-md text-black bg-transparent border-0 border-b-2 border-gray-300 appearance-none dark:text-black dark:border-gray-600 dark:focus:border-[#0099ff] focus:outline-none focus:ring-0 focus:border-[#0099ff] peer"
                placeholder=" "
                name="username"
                v-model="value"
                
              />
              <label
                for="floating-username"
                class="min-[320px]:text-xs max-[600px]:text-xs text-center absolute text-sm text-black dark:text-gray-400 duration-300 transform -translate-y-6 scale-75 top-3 -z-10 origin-[0] peer-focus:left-0 peer-focus:text-black peer-focus:dark:text-black peer-placeholder-shown:scale-100 peer-placeholder-shown:translate-y-0 peer-focus:scale-75 peer-focus:-translate-y-6"
                >Masukkan Nama masjid</label
              >
            </div>
            <div class="relative z-0 mb-6">
              <input autocomplete="off"
              ref="takjil"
                type="text"
                id="nama"
                class="min-[320px]:text-xs max-[600px]:text-xs block py-2.5 px-0 w-full text-md text-black bg-transparent border-0 border-b-2 border-gray-300 appearance-none dark:text-black dark:border-gray-600 dark:focus:border-[#0099ff] focus:outline-none focus:ring-0 focus:border-[#0099ff] peer"
                placeholder=" "
                name="username"
                v-model="value"
                
              />
              <label
                for="floating-username"
                class="min-[320px]:text-xs max-[600px]:text-xs absolute text-sm text-black dark:text-gray-400 duration-300 transform -translate-y-6 scale-75 top-3 -z-10 origin-[0] peer-focus:left-0 peer-focus:text-black peer-focus:dark:text-black peer-placeholder-shown:scale-100 peer-placeholder-shown:translate-y-0 peer-focus:scale-75 peer-focus:-translate-y-6"
                >Keunggulan</label
              >
            </div>
                <div class="flex justify-between">
                  <button @click="addNewMessage" id="tambah" class="min-[320px]:text-xs max-[600px]:text-xs text-white mr-4 p-2.5 text-sm h-8 items-center bg-cyan-700 rounded-xl hover:rounded-3xl hover:bg-cyan-900 transition-all duration-300 flex justify-center">
                 Tambahkan </button>
                  <button @click="layout = 'list'" class="mr-4 p-2.5 bg-red-400 rounded-xl hover:rounded-3xl hover:bg-red-700 transition-all duration-300 text-black inline-block">
                    <svg version="1.1" id="Layer_1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" x="0px" y="0px"
	 width="8" height="8" viewBox="0 0 50 50" enable-background="new 0 0 50 50" xml:space="preserve">

<g id="Layer_3">
	<line id="path2" fill="none" stroke="#000000" stroke-width="3" stroke-miterlimit="10" x1="8.5" y1="41.5" x2="41.5" y2="8.5"/>
	<line id="path3" fill="none" stroke="#000000" stroke-width="3" stroke-miterlimit="10" x1="41.5" y1="41.5" x2="8.5" y2="8.5"/>
</g>
</svg>
 </button>
                </div>

          </div>
        </div>
      </div>
    </div>

  </div>
  <RouterView />
  <footer class="mx-auto py-2 text-center text-cyan-700 xl:mb-0 footer min-[320px]:text-center max-[600px]:text-xs">
    <span class="copyright">Copyright {{ dateNow }} ©️. All Right Reserved.</span> <br>
    <span>v1.0.0 Made by <a href="https://www.instagram.com/syamilkffh__/" class="cursor-pointer">syamilkffh__</a>.</span>
    <br><span>web masih dalam tahap pengembangan</span>
  </footer>
</template>


<script>
import Header from "./components/header.vue"
import {getFirestore,onSnapshot,collection,doc,deleteDoc,setDoc,addDoc,orderBy,query} from 'firebase/firestore';
// Import the functions you need from the SDKs you need
import { initializeApp } from "firebase/app";
import { getAnalytics } from "firebase/analytics";
import {ref,onUnmounted} from 'vue';
// TODO: Add SDKs for Firebase products that you want to use
// https://firebase.google.com/docs/web/setup#available-libraries

// Your web app's Firebase configuration
// For Firebase JS SDK v7.20.0 and later, measurementId is optional
const firebaseConfig = {
  apiKey: "AIzaSyB1ciw9j4x4L9YtfPRFkX0bJ8rEu3QzdlE",
  authDomain: "list-96ddd.firebaseapp.com",
  projectId: "list-96ddd",
  storageBucket: "list-96ddd.appspot.com",
  messagingSenderId: "101869668771",
  appId: "1:101869668771:web:4922dc7fddf53105b2f216",
  measurementId: "G-KBPFRKQXF1"
};


const app = initializeApp(firebaseConfig);
const analytics = getAnalytics(app);
const db = getFirestore(app);

export default {
  name: 'App',
  components: {
    Header
  },
  methods: {
    addNewMessage:function() {
      addDoc(collection(db,'messages'),{
        name:this.$refs.name.value,
        takjil :this.$refs.takjil.value,
        date:Date.now()
      });      
    },
    updateMessage:function(message) {
      setDoc(doc(db,'messages',message.id),{
        name:message.name,
        takjil :message.takjil,
        date:message.date
      })
    },
    deleteMessage:function(id) {
      deleteDoc(doc(db,'messages',id))
    },
    open:function(hidden){
      const form = document.querySelector('.form')
      form.classList.remove(hidden)
    }
  },
  data:()=> {
    return {
      dateNow: new Date().getFullYear(),
      layout : 'list',
      messages:ref([])
    }
  },
  mounted() {
    const latestQuery = query(collection(db,"messages"),orderBy('date'));
    const livemessages = onSnapshot(latestQuery,(snapshot)=>{
      this.messages = snapshot.docs.map((doc) => {
        return {
          id:doc.id,
          name:doc.data().name,
          takjil:doc.data().takjil,
          date:doc.data().date
        }
      });
    });
    onUnmounted(livemessages)
  }
}
</script>