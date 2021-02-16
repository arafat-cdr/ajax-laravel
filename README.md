# ajax-laravel
 **example of ajax in laravel and send one or multiple file using ajax**


```js
   // This will also submit form images and data
   // Html form validation will also works here

   // start order form ajax
   
	$('#orderForm').submit(function(event) {
	    event.preventDefault();
	    var formData = new FormData($(this)[0]);
	    // var formData = 1;
	    console.log($(this)[0]);
		$.ajaxSetup({
	       headers: {
	          'X-CSRF-TOKEN': $('meta[name="csrf-token"]').attr('content')
	       }
	    });

	    $.ajax({
	        url: '{{ route("orderStore") }}',
	        type: 'POST',              
	        data: formData,
	        processData: false,
	        contentType: false,
	        success: function(result)
	        {
	            alert("success");
	        },
	        error: function(data)
	        {
	            alert("Failed");
	        }
	    });

	});

	// end order ajax 
```
