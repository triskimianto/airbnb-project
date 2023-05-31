<template>
    <div>
        <div class="w-full h-[80px] bg-white shadow px-6 py-6">
            <NuxtLink to="/">
                <img :src="navBrandSrc" alt="airbnb">
            </NuxtLink>
        </div>
        <div class="flex w-[1160px] mx-auto justify-between items-center mt-[70px]">
            <NuxtLink :to="`/products/${id}`">
                <button class="w-10 h-10 hover:bg-gray-100 rounded-full p-1.5">
                    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor" class="w-6 h-6 fill-[#484848]">
                        <path fill-rule="evenodd" d="M7.72 12.53a.75.75 0 010-1.06l7.5-7.5a.75.75 0 111.06 1.06L9.31 12l6.97 6.97a.75.75 0 11-1.06 1.06l-7.5-7.5z" clip-rule="evenodd" />
                    </svg>
                </button>
            </NuxtLink>
            <div class="w-[1120px] mx-auto">                
                <h1 class="text-[#484848] text-[32px] font-medium leading-9">Ajukan Pemesanan</h1>
            </div>
        </div>
        <div class="flex w-[1120px] mx-auto pl-[20px] mt-[48px] mb-[64px] xl:mb-[113px]">            
            <div class="w-[560px]">
                <section>
                    <div class="flex flex-col">
                        <h1 class="text-[#484848] text-[22px] font-medium leading-6">Perjalanan Anda</h1>
                        <div class="flex justify-between mt-6">
                            <div>
                                <h1 class="text-[#484848] text-[16px] font-medium leading-5">Tanggal</h1>
                                <h1 class="text-[#484848] text-[16px] font-light leading-5">21-23 Jun</h1> 
                            </div>
                            <div>
                                <h1 class="text-[#484848] text-[16px] font-medium leading-5 underline">Edit</h1>
                            </div>
                        </div>
                        <div class="flex justify-between mt-6">
                            <div>
                                <h1 class="text-[#484848] text-[16px] font-medium leading-5">Tamu</h1>
                                <h1 class="text-[#484848] text-[16px] font-light leading-5">1 Tamu</h1> 
                            </div>
                            <div>
                                <h1 class="text-[#484848] text-[16px] font-medium leading-5 underline">Edit</h1>
                            </div>
                        </div>
                    </div>
                    <hr class="mt-6">
                </section>                
                <section>
                    <div class="mt-8 mb-6">
                        <h1 class="text-[#484848] text-[22px] font-medium leading-[26px]">Masuk ke akun atau daftar untuk memesan</h1>
                        <div class="mt-6">                                                    
                            <div>
                                <div class="w-full relative">
                                    <select name="country" id="country" class="w-full relative appearance-none border border-gray-200 rounded-t-[8px] font-normal p-2.5">
                                        <option value="62ID">Indonesia (+62)</option>
                                        <option value="93AF">Afganistan (+93)</option>
                                        <option value="27ZA">Afrika Selatan (+27)</option>
                                        <option value="355AL">Albania (+355)</option>
                                        <option value="213DZ">Aljazair (+213)</option>
                                        <option value="1US">Amerika Serikat (+1)</option>
                                        <option value="376AD">Andorra (+376)</option>
                                        <option value="244AO">Angola (+244)</option>
                                        <option value="1AI">Anguilla (+1)</option>
                                        <option value="1AG">Antigua dan Barbuda (+1)</option>
                                        <option value="966SA">Arab Saudi (+966)</option>
                                        <option value="54AR">Argentina (+54)</option>
                                        <option value="374AM">Armenia (+374)</option>
                                        <option value="297AW">Aruba (+297)</option>
                                        <option value="61AU">Australia (+61)</option>
                                        <option value="43AT">Austria (+43)</option>
                                        <option value="994AZ">Azerbaijan (+994)</option>
                                        <option value="1BS">Bahama (+1)</option>
                                        <option value="973BH">Bahrain (+973)</option>
                                        <option value="880BD">Bangladesh (+880)</option>
                                        <option value="1BB">Barbados (+1)</option>
                                        <option value="31NL">Belanda (+31)</option>
                                        <option value="375BY">Belarus (+375)</option>
                                        <option value="32BE">Belgia (+32)</option>
                                        <option value="501BZ">Belize (+501)</option>
                                        <option value="229BJ">Benin (+229)</option>
                                        <option value="1BM">Bermuda (+1)</option>
                                        <option value="975BT">Bhutan (+975)</option>
                                        <option value="591BO">Bolivia (+591)</option>
                                        <option value="599BQ">Bonaire, Sint Eustatius, dan Saba (+599)</option>
                                        <option value="387BA">Bosnia dan Herzegovina (+387)</option>
                                        <option value="267BW">Botswana (+267)</option>
                                        <option value="55BR">Brasil (+55)</option>
                                        <option value="673BN">Brunei (+673)</option>
                                        <option value="359BG">Bulgaria (+359)</option>
                                        <option value="226BF">Burkina Faso (+226)</option>
                                        <option value="257BI">Burundi (+257)</option>
                                        <option value="235TD">Cad (+235)</option>
                                        <option value="420CZ">Ceko (+420)</option>
                                        <option value="56CL">Cile (+56)</option>
                                        <option value="242CG">Kongo (+242)</option>
                                        <option value="225CI">Côte d’Ivoire (+225)</option>
                                        <option value="599CW">Curaçao (+599)</option>
                                        <option value="243CD">Republik Demokratik Kongo (+243)</option>
                                        <option value="45DK">Denmark (+45)</option>
                                        <option value="1DM">Dominika (+1)</option>
                                        <option value="593EC">Ekuador (+593)</option>
                                        <option value="503SV">El Salvador (+503)</option>
                                        <option value="291ER">Eritrea (+291)</option>
                                        <option value="372EE">Estonia (+372)</option>
                                        <option value="268SZ">eSwatini (+268)</option>
                                        <option value="251ET">Etiopia (+251)</option>
                                        <option value="679FJ">Fiji (+679)</option>
                                        <option value="63PH">Filipina (+63)</option>
                                        <option value="358FI">Finlandia (+358)</option>
                                        <option value="241GA">Gabon (+241)</option>
                                        <option value="220GM">Gambia (+220)</option>
                                        <option value="995GE">Georgia (+995)</option>
                                        <option value="500GS">Georgia Selatan &amp; Kep. Sandwich Selatan (+500)</option>
                                        <option value="233GH">Ghana (+233)</option>
                                        <option value="350GI">Gibraltar (+350)</option>
                                        <option value="1GD">Grenada (+1)</option>
                                        <option value="299GL">Grinlandia (+299)</option>
                                        <option value="590GP">Guadeloupe (+590)</option>
                                        <option value="1GU">Guam (+1)</option>
                                        <option value="502GT">Guatemala (+502)</option>
                                        <option value="44GG">Guernsey (+44)</option>
                                        <option value="224GN">Guinea (+224)</option>
                                        <option value="240GQ">Guinea Ekuatorial (+240)</option>
                                        <option value="245GW">Guinea-Bissau (+245)</option>
                                        <option value="592GY">Guyana (+592)</option>
                                        <option value="594GF">Guyana Prancis (+594)</option>
                                        <option value="509HT">Haiti (+509)</option>
                                        <option value="504HN">Honduras (+504)</option>
                                        <option value="852HK">Hong Kong (+852)</option>
                                        <option value="36HU">Hungaria (+36)</option>
                                        <option value="91IN">India (+91)</option>
                                        <option value="62ID">Indonesia (+62)</option>
                                        <option value="44GB">Inggris Raya (+44)</option>
                                        <option value="964IQ">Irak (+964)</option>
                                        <option value="353IE">Irlandia (+353)</option>
                                        <option value="354IS">Islandia (+354)</option>
                                        <option value="972IL">Israel (+972)</option>
                                        <option value="39IT">Italia (+39)</option>
                                        <option value="1JM">Jamaika (+1)</option>
                                        <option value="81JP">Jepang (+81)</option>
                                        <option value="49DE">Jerman (+49)</option>
                                        <option value="44JE">Jersey (+44)</option>
                                        <option value="253DJ">Jibuti (+253)</option>
                                        <option value="687NC">Kaledonia Baru (+687)</option>
                                        <option value="855KH">Kamboja (+855)</option>
                                        <option value="237CM">Kamerun (+237)</option>
                                        <option value="1CA">Kanada (+1)</option>
                                        <option value="7KZ">Kazakstan (+7)</option>
                                        <option value="254KE">Kenya (+254)</option>
                                        <option value="358AX">Kepulauan Aland (+358)</option>
                                        <option value="1KY">Kepulauan Cayman (+1)</option>
                                        <option value="61CC">Kepulauan Cocos (Keeling) (+61)</option>
                                        <option value="682CK">Kepulauan Cook (+682)</option>
                                        <option value="500FK">Kepulauan Falkland (+500)</option>
                                        <option value="298FO">Kepulauan Faroe (+298)</option>
                                        <option value="1MP">Kepulauan Mariana Utara (+1)</option>
                                        <option value="692MH">Kepulauan Marshall (+692)</option>
                                        <option value="672NF">Kepulauan Norfolk (+672)</option>
                                        <option value="64PN">Kepulauan Pitcairn (+64)</option>
                                        <option value="677SB">Kepulauan Solomon (+677)</option>
                                        <option value="47SJ">Kepulauan Svalbard dan Jan Mayen (+47)</option>
                                        <option value="1TC">Kepulauan Turks dan Caicos (+1)</option>
                                        <option value="1VI">Kepulauan Virgin Amerika Serikat (+1)</option>
                                        <option value="1VG">Kepulauan Virgin Britania Raya (+1)</option>
                                        <option value="681WF">Kepulauan Wallis dan Futuna (+681)</option>
                                        <option value="996KG">Kirgistan (+996)</option>
                                        <option value="686KI">Kiribati (+686)</option>
                                        <option value="57CO">Kolombia (+57)</option>
                                        <option value="269KM">Komoro (+269)</option>
                                        <option value="82KR">Korea Selatan (+82)</option>
                                        <option value="383XK">Kosovo (+383)</option>
                                        <option value="506CR">Kosta Rika (+506)</option>
                                        <option value="385HR">Kroasia (+385)</option>
                                        <option value="53CU">Kuba (+53)</option>
                                        <option value="965KW">Kuwait (+965)</option>
                                        <option value="856LA">Laos (+856)</option>
                                        <option value="371LV">Latvia (+371)</option>
                                        <option value="961LB">Lebanon (+961)</option>
                                        <option value="266LS">Lesotho (+266)</option>
                                        <option value="231LR">Liberia (+231)</option>
                                        <option value="218LY">Libia (+218)</option>
                                        <option value="423LI">Liechtenstein (+423)</option>
                                        <option value="370LT">Lituania (+370)</option>
                                        <option value="352LU">Luksemburg (+352)</option>
                                        <option value="853MO">Makau (+853)</option>
                                        <option value="389MK">Makedonia Utara (+389)</option>
                                        <option value="261MG">Madagaskar (+261)</option>
                                        <option value="960MV">Maladewa (+960)</option>
                                        <option value="265MW">Malawi (+265)</option>
                                        <option value="60MY">Malaysia (+60)</option>
                                        <option value="223ML">Mali (+223)</option>
                                        <option value="356MT">Malta (+356)</option>
                                        <option value="212MA">Maroko (+212)</option>
                                        <option value="596MQ">Martinik (+596)</option>
                                        <option value="222MR">Mauritania (+222)</option>
                                        <option value="230MU">Mauritius (+230)</option>
                                        <option value="262YT">Mayotte (+262)</option>
                                        <option value="52MX">Meksiko (+52)</option>
                                        <option value="20EG">Mesir (+20)</option>
                                        <option value="691FM">Mikronesia (+691)</option>
                                        <option value="373MD">Moldova (+373)</option>
                                        <option value="377MC">Monako (+377)</option>
                                        <option value="976MN">Mongolia (+976)</option>
                                        <option value="382ME">Montenegro (+382)</option>
                                        <option value="1MS">Montserrat (+1)</option>
                                        <option value="258MZ">Mozambik (+258)</option>
                                        <option value="95MM">Myanmar (Burma) (+95)</option>
                                        <option value="264NA">Namibia (+264)</option>
                                        <option value="674NR">Nauru (+674)</option>
                                        <option value="977NP">Nepal (+977)</option>
                                        <option value="227NE">Niger (+227)</option>
                                        <option value="234NG">Nigeria (+234)</option>
                                        <option value="505NI">Nikaragua (+505)</option>
                                        <option value="683NU">Niue (+683)</option>
                                        <option value="47NO">Norwegia (+47)</option>
                                        <option value="968OM">Oman (+968)</option>
                                        <option value="92PK">Pakistan (+92)</option>
                                        <option value="680PW">Palau (+680)</option>
                                        <option value="507PA">Panama (+507)</option>
                                        <option value="675PG">Papua Nugini (+675)</option>
                                        <option value="595PY">Paraguay (+595)</option>
                                        <option value="51PE">Peru (+51)</option>
                                        <option value="48PL">Polandia (+48)</option>
                                        <option value="689PF">Polinesia Prancis (+689)</option>
                                        <option value="351PT">Portugal (+351)</option>
                                        <option value="33FR">Prancis (+33)</option>
                                        <option value="1PR">Puerto Riko (+1)</option>
                                        <option value="44IM">Pulau Man (+44)</option>
                                        <option value="61CX">Pulau Natal (+61)</option>
                                        <option value="974QA">Qatar (+974)</option>
                                        <option value="236CF">Republik Afrika Tengah (+236)</option>
                                        <option value="1DO">Republik Dominika (+1)</option>
                                        <option value="262RE">Réunion (+262)</option>
                                        <option value="40RO">Rumania (+40)</option>
                                        <option value="7RU">Rusia (+7)</option>
                                        <option value="250RW">Rwanda (+250)</option>
                                        <option value="212EH">Sahara Barat (+212)</option>
                                        <option value="590BL">Saint Barthélemy (+590)</option>
                                        <option value="290SH">Saint Helena (+290)</option>
                                        <option value="1KN">Saint Kitts dan Nevis (+1)</option>
                                        <option value="1LC">Saint Lucia (+1)</option>
                                        <option value="590MF">Saint Martin (+590)</option>
                                        <option value="508PM">Saint Pierre dan Miquelon (+508)</option>
                                        <option value="1VC">Saint Vincent dan Grenadine (+1)</option>
                                        <option value="685WS">Samoa (+685)</option>
                                        <option value="1AS">Samoa Amerika (+1)</option>
                                        <option value="378SM">San Marino (+378)</option>
                                        <option value="239ST">Sao Tome dan Principe (+239)</option>
                                        <option value="64NZ">Selandia Baru (+64)</option>
                                        <option value="221SN">Senegal (+221)</option>
                                        <option value="381RS">Serbia (+381)</option>
                                        <option value="248SC">Seychelles (+248)</option>
                                        <option value="232SL">Sierra Leone (+232)</option>
                                        <option value="65SG">Singapura (+65)</option>
                                        <option value="1SX">Sint Maarten (+1)</option>
                                        <option value="357CY">Siprus (+357)</option>
                                        <option value="421SK">Slovakia (+421)</option>
                                        <option value="386SI">Slovenia (+386)</option>
                                        <option value="252SO">Somalia (+252)</option>
                                        <option value="34ES">Spanyol (+34)</option>
                                        <option value="94LK">Sri Lanka (+94)</option>
                                        <option value="249SD">Sudan (+249)</option>
                                        <option value="211SS">Sudan Selatan (+211)</option>
                                        <option value="597SR">Suriname (+597)</option>
                                        <option value="46SE">Swedia (+46)</option>
                                        <option value="41CH">Swiss (+41)</option>
                                        <option value="886TW">Taiwan (+886)</option>
                                        <option value="992TJ">Tajikistan (+992)</option>
                                        <option value="238CV">Tanjung Verde (+238)</option>
                                        <option value="255TZ">Tanzania (+255)</option>
                                        <option value="66TH">Thailand (+66)</option>
                                        <option value="670TL">Timor Leste (+670)</option>
                                        <option value="86CN">Tiongkok (+86)</option>
                                        <option value="228TG">Togo (+228)</option>
                                        <option value="690TK">Tokelau (+690)</option>
                                        <option value="676TO">Tonga (+676)</option>
                                        <option value="1TT">Trinidad dan Tobago (+1)</option>
                                        <option value="216TN">Tunisia (+216)</option>
                                        <option value="90TR">Turki (+90)</option>
                                        <option value="993TM">Turkimenistan (+993)</option>
                                        <option value="688TV">Tuvalu (+688)</option>
                                        <option value="256UG">Uganda (+256)</option>
                                        <option value="380UA">Ukraina (+380)</option>
                                        <option value="971AE">Uni Emirat Arab (+971)</option>
                                        <option value="598UY">Uruguay (+598)</option>
                                        <option value="998UZ">Uzbekistan (+998)</option>
                                        <option value="678VU">Vanuatu (+678)</option>
                                        <option value="379VA">Vatikan (+379)</option>
                                        <option value="58VE">Venezuela (+58)</option>
                                        <option value="84VN">Vietnam (+84)</option>
                                        <option value="246IO">Wilayah Inggris di Samudra Hindia (+246)</option>
                                        <option value="970PS">Wilayah Palestina (+970)</option>
                                        <option value="967YE">Yaman (+967)</option>
                                        <option value="962JO">Yordania (+962)</option>
                                        <option value="30GR">Yunani (+30)</option>
                                        <option value="260ZM">Zambia (+260)</option>
                                        <option value="263ZW">Zimbabwe (+263)</option>
                                    </select>
                                    <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-4 h-4 absolute top-[50%] translate-y-[-50%] right-2.5">
                                        <path stroke-linecap="round" stroke-linejoin="round" d="M19.5 8.25l-7.5 7.5-7.5-7.5" />
                                    </svg>
                                </div>
                                <div>
                                    <input type="text" class="w-full border border-gray-200 rounded-b-[8px] font-normal p-2.5" placeholder="Nomor telepon">
                                </div>
                            </div>
                            <div class="mt-2">
                                <h1 class="text-[#484848] text-[12px] font-normal leading-[16px]">
                                    Kami akan menelepon atau mengirim SMS guna mengonfirmasikan nomor Anda. Tarif standar SMS dan data berlaku. 
                                    <NuxLink to="#" class="font-medium underline cursor-pointer">Kebijakan Privasi</NuxLink>
                                </h1>
                            </div>
                            <div class="mt-4 mb-6">
                                <div class="w-full">
                                    <MainCTA :btnTitle="btnTitle" />
                                </div>
                            </div>
                            <div class="mt-4 mb-4">
                                <div class="inline-flex items-center justify-center w-full">
                                    <hr class="w-full border bg-gray-200">
                                    <span class="absolute bg-white text-[#484848] text-[12px] font-normal leading-4 px-4 ">atau</span>
                                </div>
                            </div>
                            <div class="w-full">
                                <div class="grid grid-cols-3 gap-x-5">
                                    <NuxtLink to="#" class="w-full">
                                        <div class="bg-white hover:bg-gray-200 border border-[#484848] rounded-[8px] px-[23px] py-[13px]">
                                            <div class="flex justify-center">
                                                <svg viewBox="0 0 32 32" xmlns="http://www.w3.org/2000/svg" aria-hidden="true" role="presentation" focusable="false" fill="currentColor"  class="w-5 h-5">
                                                    <path fill="#1877F2" d="M32 0v32H0V0z"></path><path d="M22.938 16H18.5v-3.001c0-1.266.62-2.499 2.607-2.499h2.018V6.562s-1.831-.312-3.582-.312c-3.654 0-6.043 2.215-6.043 6.225V16H9.436v4.625H13.5V32h5V20.625h3.727l.71-4.625z" fill="#FFF"></path>
                                                </svg>
                                            </div>
                                        </div>
                                    </NuxtLink>
                                    <NuxtLink to="#" class="w-full">
                                        <div class="bg-white hover:bg-gray-200 border border-[#484848] rounded-[8px] px-[23px] py-[13px]">
                                            <div class="flex justify-center">
                                                <svg viewBox="0 0 32 32" xmlns="http://www.w3.org/2000/svg" aria-hidden="true" role="presentation" focusable="false" fill="currentColor"  class="w-5 h-5"><g transform="translate(4.376957 4.073369)">
                                                    <path d="m19.7480429 20.9266305c2.813-2.625 4.063-7 3.313-11.18799996h-11.188v4.62599996h6.375c-.25 1.5-1.125 2.75-2.375 3.562z" fill="#4285f4"></path><path d="m1.24804285 17.2396305c.82223 1.6196 2.0014 3.0314 3.4486 4.129s3.1247 1.8523 4.906 2.2073c1.78130005.355 3.62000005.301 5.37740005-.1579s3.3877-1.3108 4.768-2.4914l-3.875-3c-3.313 2.188-8.81300005 1.375-10.68800005-3.75z" fill="#34a853"></path><path d="m5.18573285 14.1766305c-.5-1.563-.5-3 0-4.56299996l-3.938-3.062c-1.438 2.875-1.875 6.93799996 0 10.68799996z" fill="#fbbc02"></path><path d="m5.18604285 9.61463054c1.374-4.31301 7.25000005-6.81301 11.18700005-3.126l3.438-3.37401c-4.875-4.688-14.37500005-4.5-18.56300005 3.43601l3.938 3.063z" fill="#ea4335"></path></g>
                                                </svg>
                                            </div>
                                        </div>
                                    </NuxtLink>
                                    <NuxtLink to="#" class="w-full">
                                        <div class="bg-white hover:bg-gray-200 border border-[#484848] rounded-[8px] px-[23px] py-[13px]">
                                            <div class="flex justify-center">
                                                <svg viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg" role="presentation" aria-hidden="true" fill="currentColor" focusable="false" class="w-5 h-5">
                                                    <path d="m13.3 2.1a5.1 5.1 0 0 1 3.8-2.1 5.1 5.1 0 0 1 -1.2 3.8 4.1 4.1 0 0 1 -3.6 1.7 4.5 4.5 0 0 1 1-3.4zm-5 3.7c-2.8 0-5.8 2.5-5.8 7.3 0 4.9 3.5 10.9 6.3 10.9 1 0 2.5-1 4-1s2.6.9 4 .9c3.1 0 5.3-6.4 5.3-6.4a5.3 5.3 0 0 1 -3.2-4.9 5.2 5.2 0 0 1 2.6-4.5 5.4 5.4 0 0 0 -4.7-2.4c-2 0-3.5 1.1-4.3 1.1-.9 0-2.4-1-4.2-1z"></path>
                                                </svg>
                                            </div>
                                        </div>
                                    </NuxtLink>
                                </div>                                
                            </div>
                            <div class="w-full mt-4">
                                <NuxLink to="#" class="w-full">
                                    <div class="w-full bg-white hover:bg-gray-200 border border-[#484848] rounded-[8px] px-[23px] py-[13px]">                                        
                                        <div class="flex">
                                            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 32 32" aria-hidden="true" role="presentation" focusable="false" fill="currentColor"  class="w-5 h-5">
                                                <path d="M30.5105,5.87921A5.06207,5.06207,0,0,0,26,3H6A5.06215,5.06215,0,0,0,1.48932,5.87946,4.9444,4.9444,0,0,0,1,8V24a5.00588,5.00588,0,0,0,5,5H26a5.00588,5.00588,0,0,0,5-5V8A4.94373,4.94373,0,0,0,30.5105,5.87921ZM6,5H26a2.97234,2.97234,0,0,1,1.77252.59253l-9.8194,8.41675a2.98373,2.98373,0,0,1-3.90527,0l-9.82013-8.417A2.97238,2.97238,0,0,1,6,5ZM29,24a3.00328,3.00328,0,0,1-3,3H6a3.00328,3.00328,0,0,1-3-3V8a2.96566,2.96566,0,0,1,.10266-.73773l9.64343,8.26556a4.97272,4.97272,0,0,0,6.50782,0L28.89728,7.262A2.96542,2.96542,0,0,1,29,8Z"></path>
                                            </svg>
                                            <div class="flex w-full justify-center">
                                                <h1 class="text-[#484848] text-[14px] font-medium leading-5">Lanjutkan dengan email</h1>
                                            </div>
                                        </div>                                        
                                    </div>
                                </NuxLink>
                            </div>
                        </div>
                    </div>
                </section>
            </div>
            <div class="w-[466.656px] ml-[93.3281px]">
                <div class="w-full border border-gray-200 rounded-[12px] p-6">
                    <div class="flex w-full">
                        <img class="w-[124px] h-[106px] object-contain rounded-[8px]" :src="selectedId.image" alt="">
                        <div class="flex flex-col h-[106px] ml-3">
                            <div class="h-[56px]">
                                <h1 class="text-[#c4c4c4] text-[12px] leading-4">Kamar di rumah liburan</h1>
                                <h1 class="text-[#484848] text-[14px] leading-[18px] mt-1">Book for id: {{ id }} - {{ selectedId.title }}</h1>
                            </div>
                            <div class="flex h-full">
                                <div class="flex items-end">
                                    <div class="flex items-center gap-x-2">
                                        <div class="flex items-center gap-x-1">
                                            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor" class="w-2.5 h-2.5">
                                                <path fill-rule="evenodd" d="M10.788 3.21c.448-1.077 1.976-1.077 2.424 0l2.082 5.007 5.404.433c1.164.093 1.636 1.545.749 2.305l-4.117 3.527 1.257 5.273c.271 1.136-.964 2.033-1.96 1.425L12 18.354 7.373 21.18c-.996.608-2.231-.29-1.96-1.425l1.257-5.273-4.117-3.527c-.887-.76-.415-2.212.749-2.305l5.404-.433 2.082-5.006z" clip-rule="evenodd" />
                                            </svg>
                                            <h1 class="text-[#484848] text-[12px] font-normal leading-4">{{ selectedId.rating.rate }}<span class="font-light"> ({{ selectedId.rating.count }} ulasan)</span></h1>
                                        </div>                                        
                                        <div>
                                            <h1>•</h1>
                                        </div>
                                        <div class="flex items-center gap-x-1">
                                            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor" class="w-2.5 h-2.5">
                                                <path fill-rule="evenodd" d="M5.166 2.621v.858c-1.035.148-2.059.33-3.071.543a.75.75 0 00-.584.859 6.753 6.753 0 006.138 5.6 6.73 6.73 0 002.743 1.346A6.707 6.707 0 019.279 15H8.54c-1.036 0-1.875.84-1.875 1.875V19.5h-.75a2.25 2.25 0 00-2.25 2.25c0 .414.336.75.75.75h15a.75.75 0 00.75-.75 2.25 2.25 0 00-2.25-2.25h-.75v-2.625c0-1.036-.84-1.875-1.875-1.875h-.739a6.706 6.706 0 01-1.112-3.173 6.73 6.73 0 002.743-1.347 6.753 6.753 0 006.139-5.6.75.75 0 00-.585-.858 47.077 47.077 0 00-3.07-.543V2.62a.75.75 0 00-.658-.744 49.22 49.22 0 00-6.093-.377c-2.063 0-4.096.128-6.093.377a.75.75 0 00-.657.744zm0 2.629c0 1.196.312 2.32.857 3.294A5.266 5.266 0 013.16 5.337a45.6 45.6 0 012.006-.343v.256zm13.5 0v-.256c.674.1 1.343.214 2.006.343a5.265 5.265 0 01-2.863 3.207 6.72 6.72 0 00.857-3.294z" clip-rule="evenodd" />
                                            </svg>
                                            <h1 class="text-[#484848] text-[12px] font-normal leading-4">HosTeladan</h1>
                                        </div>                                        
                                    </div>                                    
                                </div>                                                                
                            </div>                            
                        </div>                        
                    </div>    
                    <hr class="mt-6">    
                    <div class="mt-6">
                        <h1 class="text-[#484848] text-[22px] font-medium leading-[26px]">Perjalanan Anda</h1>
                        <div class="flex justify-between mt-6">
                            <div class="flex gap-x-1">
                                <h1 class="text-[#484848] text-[16px] font-normal leading-5">Rp {{ formatPrice(selectedId.price * 14996) }}</h1>
                                <h1 class="text-[#484848] text-[16px] font-normal leading-5">x</h1>
                                <h1 class="text-[#484848] text-[16px] font-normal leading-5">3 malam</h1>
                            </div>
                            <div class="flex">
                                <h1 class="text-[#484848] text-[16px] font-normal leading-5">Rp {{ formatPrice(selectedId.price * 14996 * 3) }}</h1>
                            </div>                            
                        </div>
                        <hr class="mt-6">
                        <div class="flex justify-between mt-6">
                            <div class="flex gap-x-1">
                                <h1 class="text-[#484848] text-[16px] font-medium leading-5">Total</h1>
                                <NuxtLink :to="`#`" class="text-[#484848] text-[16px] font-medium leading-5 underline">(IDR)</NuxtLink>
                            </div>
                            <div class="flex">
                                <h1 class="text-[#484848] text-[16px] font-medium leading-5">Rp {{ formatPrice(selectedId.price * 14996 * 3) }}</h1>
                            </div>                            
                        </div>
                    </div>                                
                </div>                
            </div>
        </div>
        <footer class="w-full bg-gray-50 border border-t-gray-300">
            <div class="w-[1189px] mx-auto py-6">
                <h1 class="text-[#484848] text-[14px] font-normal leading-[18px]">&copy; 2023 Airbnb, Inc.</h1>
            </div>
        </footer>
    </div>    
</template>

<script setup>
    import navBrandSrc from '/icons/airbnb-nav-red-text.png';

    const btnTitle = "Lanjutkan";

    const route = useRoute();
    const id = route.params.id;
    const { data:selectedId } = await useFetch('https://fakestoreapi.com/products/'+id);

    let formatPrice = (price) => {
        let result = Math.floor(price)
        return result.toLocaleString('id-ID', { useGrouping: true })
    };

    useHead({
        title: "Permohonan pemesanan",
    })
</script>