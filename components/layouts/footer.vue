<!-- components/Footer.vue -->
<template>
  <footer class="text-black p-8">
    <!-- Logo -->
    <div class="flex items-center justify-center mb-4">
      <img src="/logo1.png" alt="Logo" class="h-24 md:h-36 w-auto" />
    </div>

    <!-- Menu -->
    <div class="flex flex-wrap justify-center mb-8">
      <!-- Menu 1-6 -->
      <div class="w-1/2 md:w-1/6 px-4 mb-4 md:mb-0">
        <a href="#" class="block text-gray-500 mb-3 text-xs hover:text-black">CONTACT US</a>
        <a href="#" class="block text-gray-500 mb-3 text-xs hover:text-black">SUBSCRIBE TO NEWSLETTER</a>
      </div>
        <div class="w-1/2 md:w-1/6 px-4 mb-4 md:mb-0">
        <a href="#" class="block text-gray-500 mb-3 text-xs hover:text-black">LOYALTY PROGRAM</a>
        <a href="#" class="block text-gray-500 mb-3 text-xs hover:text-black">PRESS</a>
        </div>
        <div class="w-1/2 md:w-1/6 px-4 mb-4 md:mb-0">
        <a href="#" class="block text-gray-500 mb-3 text-xs hover:text-black">SHIPPING & DELIVERY</a>
        <a href="#" class="block text-gray-500 mb-3 text-xs hover:text-black">EXCHANGE POLICY</a>
        </div>
        <div class="w-1/2 md:w-1/6 px-4 mb-4 md:mb-0">
        <a href="#" class="block text-gray-500 mb-3 text-xs hover:text-black">CARE INSTRUCTIONS</a>
        <a href="#" class="block text-gray-500 mb-3 text-xs hover:text-black">FAQ</a>
        </div>
        <div class="w-1/2 md:w-1/6 px-4 mb-4 md:mb-0">
        <a href="#" class="block text-gray-500 mb-3 text-xs hover:text-black">TERMS OF SERVICE</a>
        <a href="#" class="block text-gray-500 mb-3 text-xs hover:text-black">REFUND POLICY</a>
        </div>
        <div class="w-1/2 md:w-1/6 px-4 mb-4 md:mb-0">
        <a href="#" class="block text-gray-500 mb-3 text-xs hover:text-black">ORDER & PAYMENT</a>
        <a href="#" class="block text-gray-500 mb-3 text-xs hover:text-black">STOCKIST</a>
        </div>
    </div>

    <!-- Media Sosial -->
    <div class="flex items-center justify-center md:justify-start space-x-4 my-9">
      <a href="#" class="text-gray-500 hover:text-black">
        <svg xmlns="http://www.w3.org/2000/svg" x="0px" y="0px" width="25" height="auto" viewBox="0 0 50 50">
            <path d="M32,11h5c0.552,0,1-0.448,1-1V3.263c0-0.524-0.403-0.96-0.925-0.997C35.484,2.153,32.376,2,30.141,2C24,2,20,5.68,20,12.368 V19h-7c-0.552,0-1,0.448-1,1v7c0,0.552,0.448,1,1,1h7v19c0,0.552,0.448,1,1,1h7c0.552,0,1-0.448,1-1V28h7.222 c0.51,0,0.938-0.383,0.994-0.89l0.778-7C38.06,19.518,37.596,19,37,19h-8v-5C29,12.343,30.343,11,32,11z"></path>
        </svg>
      </a>
      <a href="#" class="text-gray-500 hover:text-black">
        <svg xmlns="http://www.w3.org/2000/svg" x="0px" y="0px" width="25" height="auto" viewBox="0 0 50 50">
        <path d="M 16 3 C 8.8324839 3 3 8.8324839 3 16 L 3 34 C 3 41.167516 8.8324839 47 16 47 L 34 47 C 41.167516 47 47 41.167516 47 34 L 47 16 C 47 8.8324839 41.167516 3 34 3 L 16 3 z M 16 5 L 34 5 C 40.086484 5 45 9.9135161 45 16 L 45 34 C 45 40.086484 40.086484 45 34 45 L 16 45 C 9.9135161 45 5 40.086484 5 34 L 5 16 C 5 9.9135161 9.9135161 5 16 5 z M 37 11 A 2 2 0 0 0 35 13 A 2 2 0 0 0 37 15 A 2 2 0 0 0 39 13 A 2 2 0 0 0 37 11 z M 25 14 C 18.936712 14 14 18.936712 14 25 C 14 31.063288 18.936712 36 25 36 C 31.063288 36 36 31.063288 36 25 C 36 18.936712 31.063288 14 25 14 z M 25 16 C 29.982407 16 34 20.017593 34 25 C 34 29.982407 29.982407 34 25 34 C 20.017593 34 16 29.982407 16 25 C 16 20.017593 20.017593 16 25 16 z"></path>
        </svg>
      </a>
      <a href="#" class="text-gray-500 hover:text-black">
        <svg xmlns="http://www.w3.org/2000/svg" x="0px" y="0px" width="25" height="auto" viewBox="0 0 32 32">
        <path d="M 16.09375 4 C 11.01675 4 6 7.3833281 6 12.861328 C 6 16.344328 7.9584844 18.324219 9.1464844 18.324219 C 9.6364844 18.324219 9.9199219 16.958266 9.9199219 16.572266 C 9.9199219 16.112266 8.7460938 15.131797 8.7460938 13.216797 C 8.7460938 9.2387969 11.774359 6.4199219 15.693359 6.4199219 C 19.063359 6.4199219 21.556641 8.3335625 21.556641 11.851562 C 21.556641 14.478563 20.501891 19.40625 17.087891 19.40625 C 15.855891 19.40625 14.802734 18.516234 14.802734 17.240234 C 14.802734 15.370234 16 13.558906 16 11.628906 C 16 8.3529063 11.462891 8.94725 11.462891 12.90625 C 11.462891 13.73725 11.5665 14.657063 11.9375 15.414062 C 11.2555 18.353063 10 23.037406 10 26.066406 C 10 27.001406 10.133656 27.921422 10.222656 28.857422 C 10.390656 29.045422 10.307453 29.025641 10.564453 28.931641 C 13.058453 25.517641 12.827078 24.544172 13.955078 20.076172 C 14.564078 21.234172 16.137766 21.857422 17.384766 21.857422 C 22.639766 21.857422 25 16.736141 25 12.119141 C 25 7.2061406 20.75475 4 16.09375 4 z"></path>
        </svg>
      </a>
      <a href="#" class="text-gray-500 hover:text-black">
        <svg xmlns="http://www.w3.org/2000/svg" x="0px" y="0px" width="25" height="auto" viewBox="0 0 24 24">
            <path d="M21,5c0,0-3-1-9-1S3,5,3,5s-1,3-1,7s1,7,1,7s3,1,9,1s9-1,9-1s1-3,1-7S21,5,21,5z M10,15.464V8.536L16,12L10,15.464z"></path>
        </svg>
      </a>
      <a href="#" class="text-gray-500 hover:text-black">
        <svg xmlns="http://www.w3.org/2000/svg" x="0px" y="0px" width="25" height="auto" viewBox="0,0,256,256">
        <g fill="none" fill-rule="nonzero" stroke="none" stroke-width="1" stroke-linecap="butt" stroke-linejoin="miter" stroke-miterlimit="10" stroke-dasharray="" stroke-dashoffset="0" font-family="none" font-weight="none" font-size="none" text-anchor="none" style="mix-blend-mode: normal"><g transform="scale(5.33333,5.33333)"><path d="M20,37c2.761,0 5,-2.239 5,-5v-1v-1v-23.93h5.208c-0.031,-0.14 -0.072,-0.276 -0.097,-0.419h-0.001c-0.044,-0.248 -0.076,-0.495 -0.099,-0.746v-0.835h-7.011v23.93v1v1c0,2.761 -2.239,5 -5,5c-0.864,0 -1.665,-0.239 -2.375,-0.625c0.848,1.556 2.478,2.625 4.375,2.625z" fill="#ffffff"></path><path d="M33.718,11.407c-0.797,-1.094 -1.364,-2.367 -1.607,-3.756h-0.001c-0.044,-0.248 -0.076,-0.495 -0.099,-0.746v-0.835h-1.803c0.491,2.182 1.761,4.062 3.51,5.337z" fill="#000000"></path><path d="M18,25c-2.761,0 -5,2.239 -5,5c0,1.897 1.069,3.527 2.625,4.375c-0.386,-0.71 -0.625,-1.511 -0.625,-2.375c0,-2.761 2.239,-5 5,-5c0.343,0 0.677,0.035 1,0.101v-7.05c-0.331,-0.028 -0.662,-0.051 -1,-0.051c-0.338,0 -0.669,0.023 -1,0.05v5.05c-0.323,-0.065 -0.657,-0.1 -1,-0.1z" fill="#000000"></path><path d="M36.257,13.783c0.867,0.541 1.819,0.908 2.806,1.131v-0.376v-0.002v-1.381c-1.7,0.003 -3.364,-0.473 -4.806,-1.373c-0.186,-0.116 -0.361,-0.247 -0.538,-0.376c0.687,0.945 1.544,1.757 2.538,2.377z" fill="#ffffff"></path><path d="M19,20.05v-2c-0.331,-0.027 -0.662,-0.05 -1,-0.05c-6.627,0 -12,5.373 -12,12c0,3.824 1.795,7.222 4.581,9.419c-1.612,-2.042 -2.581,-4.615 -2.581,-7.419c0,-6.29 4.842,-11.44 11,-11.95z" fill="#ffffff"></path><path d="M39.062,14.914v4.733c-3.375,0 -6.501,-1.071 -9.052,-2.894l0.003,13.247l-0.014,-0.018c0,0.006 0.001,0.012 0.001,0.018c0,6.627 -5.373,12 -12,12c-2.804,0 -5.377,-0.969 -7.419,-2.581c2.197,2.786 5.595,4.581 9.419,4.581c6.627,0 12,-5.373 12,-12c0,-0.006 -0.001,-0.012 -0.001,-0.018l0.014,0.018l-0.002,-13.248c2.551,1.823 5.677,2.894 9.052,2.894v-5.108v-0.002v-1.381c-0.678,0.002 -1.346,-0.094 -2.001,-0.241z" fill="#000000"></path><path d="M30,30c0,-0.006 -0.001,-0.012 -0.001,-0.018l0.014,0.018l-0.002,-13.248c2.551,1.823 5.677,2.894 9.052,2.894v-4.733c-0.987,-0.223 -1.939,-0.59 -2.806,-1.131c-0.994,-0.62 -1.851,-1.432 -2.538,-2.376c-1.75,-1.275 -3.019,-3.155 -3.51,-5.337h-5.209v23.931v1v1c0,2.761 -2.239,5 -5,5c-1.897,0 -3.527,-1.069 -4.375,-2.625c-1.556,-0.848 -2.625,-2.478 -2.625,-4.375c0,-2.761 2.239,-5 5,-5c0.343,0 0.677,0.035 1,0.101v-5.05c-6.158,0.509 -11,5.659 -11,11.949c0,2.804 0.969,5.377 2.581,7.419c2.042,1.612 4.615,2.581 7.419,2.581c6.627,0 12,-5.373 12,-12z" fill="#000000"></path></g></g>
        </svg>
      </a>
      <a href="#" class="text-gray-500 hover:text-black">
        <svg xmlns="http://www.w3.org/2000/svg" x="0px" y="0px" width="25" height="auto" viewBox="0 0 24 24">
            <path d="M 12.011719 2 C 6.5057187 2 2.0234844 6.478375 2.0214844 11.984375 C 2.0204844 13.744375 2.4814687 15.462563 3.3554688 16.976562 L 2 22 L 7.2324219 20.763672 C 8.6914219 21.559672 10.333859 21.977516 12.005859 21.978516 L 12.009766 21.978516 C 17.514766 21.978516 21.995047 17.499141 21.998047 11.994141 C 22.000047 9.3251406 20.962172 6.8157344 19.076172 4.9277344 C 17.190172 3.0407344 14.683719 2.001 12.011719 2 z M 12.009766 4 C 14.145766 4.001 16.153109 4.8337969 17.662109 6.3417969 C 19.171109 7.8517969 20.000047 9.8581875 19.998047 11.992188 C 19.996047 16.396187 16.413812 19.978516 12.007812 19.978516 C 10.674812 19.977516 9.3544062 19.642812 8.1914062 19.007812 L 7.5175781 18.640625 L 6.7734375 18.816406 L 4.8046875 19.28125 L 5.2851562 17.496094 L 5.5019531 16.695312 L 5.0878906 15.976562 C 4.3898906 14.768562 4.0204844 13.387375 4.0214844 11.984375 C 4.0234844 7.582375 7.6067656 4 12.009766 4 z M 8.4765625 7.375 C 8.3095625 7.375 8.0395469 7.4375 7.8105469 7.6875 C 7.5815469 7.9365 6.9355469 8.5395781 6.9355469 9.7675781 C 6.9355469 10.995578 7.8300781 12.182609 7.9550781 12.349609 C 8.0790781 12.515609 9.68175 15.115234 12.21875 16.115234 C 14.32675 16.946234 14.754891 16.782234 15.212891 16.740234 C 15.670891 16.699234 16.690438 16.137687 16.898438 15.554688 C 17.106437 14.971687 17.106922 14.470187 17.044922 14.367188 C 16.982922 14.263188 16.816406 14.201172 16.566406 14.076172 C 16.317406 13.951172 15.090328 13.348625 14.861328 13.265625 C 14.632328 13.182625 14.464828 13.140625 14.298828 13.390625 C 14.132828 13.640625 13.655766 14.201187 13.509766 14.367188 C 13.363766 14.534188 13.21875 14.556641 12.96875 14.431641 C 12.71875 14.305641 11.914938 14.041406 10.960938 13.191406 C 10.218937 12.530406 9.7182656 11.714844 9.5722656 11.464844 C 9.4272656 11.215844 9.5585938 11.079078 9.6835938 10.955078 C 9.7955938 10.843078 9.9316406 10.663578 10.056641 10.517578 C 10.180641 10.371578 10.223641 10.267562 10.306641 10.101562 C 10.389641 9.9355625 10.347156 9.7890625 10.285156 9.6640625 C 10.223156 9.5390625 9.737625 8.3065 9.515625 7.8125 C 9.328625 7.3975 9.131125 7.3878594 8.953125 7.3808594 C 8.808125 7.3748594 8.6425625 7.375 8.4765625 7.375 z"></path>
        </svg>
      </a>
      <!-- Tambahkan media sosial lainnya sesuai kebutuhan -->
    </div>

    <!-- Copyright -->
    <div class="md:flex justify-between items-center text-center text-sm space-y-4 md:space-y-0">
      <p class="text-gray-500">Nyawa.id 2023</p>
      <p class="text-gray-500 uppercase">&copy; 2023 - Nyawa.id developed by yukti</p>
    </div>
  </footer>
</template>

<script>
export default {
  // ...
};
</script>
