### **Web Aplikacije Zadatak [1]**

## **Preuzmi broj commitova vuejs repozitorija i prikaži rezultat**

Zadatak vam je napraviti malu Vue.js aplikaciju koja će prikazivati commitove vuejs repozitorija.

1. Aplikacija se treba sastojati od dva pagea,

2. Prvi page mora prikazivati barem 10 **SHA** commitova u obliku liste,

3. Drugi page prikazuje detalje tog commita - ime i email autora, poruku commita te datum kada je commitano,

4. Pritisak na SHA link vas vodi do detalja tog specifičnog commita

5. Treba postojati back button u drugom pageu koji vodi nazad na prvi i

6. Neka bude lijepo.

Moj prijedlog, s time da prve dvije linije nisu prijedlog :)

1. Pošalji **GET** request na: '[https://api.github.com/repos/vuejs/vue/commits](https://api.github.com/repos/vuejs/vue/commits)',

2. **Response** od tog **GET** requesta stavi u data() jednog viewa,

3. View neka čini podloga, primjerice prazan v-card kao što ima Vuetify,

4. Unutar tog v-carda neka bude jedan v-for za iteraciju nad podacima Responsea - SHA linkovima,

5. Detalji, iliti page 2, nek budu komponenta kojoj će se detalji commita proslijediti kao propsi i

6. To je više-manje to, stavi button s linkom za nazad.

Detalji ne moraju biti komponenta, samo prijedlog.

**Tip** : možete koristiti Vuetify i instalirajte si Postman: [https://www.postman.com/](https://www.postman.com/).
