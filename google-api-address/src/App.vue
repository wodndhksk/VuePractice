<template>
  <input id="autocomplete" type="text">
</template>

<script>
  export default {
    components: { 
        
    },
    data: function () {
      return {
        
      };
    },
    mounted() {
      const google = window.google
      //Google AutoComplete Place
      var autocomplete = new google.maps.places.Autocomplete(
      document.getElementById("autocomplete"),
      //{type:['geocode']}
      );

      autocomplete.addListener('place_changed', () => {
        let placeTemp = autocomplete.getPlace();
        // 주소가 들어있는 값
        let address = placeTemp.address_components;
        console.log(address);
      })
    },
    methods: {
    
    }
  };
  </script>