# html-dialog
Modal dialog based on Bootstrap.css

Sample template:
```
<script type="text/html" id="dialog-textbox-template">
	<!--dialog-textbox.html-->
	<div class="modal-content">
		<div class="modal-header">
			<button type="button" class="close metaclass-dialog-close" data-dismiss="modal" aria-label="Close">
				<span aria-hidden="true">&times;</span>
			</button>
			<h4 class="modal-title" id="title" data-dialog-value="title">
			<!-- TITLE -->
				Edit value
			<!-- TITLE -->
			</h4>
		</div>
		<form>
			<div class="modal-body">
			<!-- BODY -->
				<input type="text" id="StrBuffer"/>
			<!-- BODY -->
			</div>
			<div class="modal-footer">
			<!-- FOOTER -->
				<button class="btn btn-default" data-dialog-control="Ok">Save changes</button>
				<button class="btn btn-default" data-dialog-control="Cancel">Close</button>
			<!-- FOOTER -->
			</div>
		</form>
	</div><!-- /.modal-content -->	
</script>
```

Sample JS code:
```
	  	var DialogTextBox = function () {
		  	return window.dialogWindow.fromTemplate('dialog-textbox-template')	
		  }
```
...
```
			var data = {
				title: 'Change Playlist Name', 
				StrBuffer: 'Some value...'
			};

			console.log('Starting dialog...');
			DialogTextBox().show(data).then(function (response) {
				if(response) {
					alert(response.StrBuffer);
					console.log('New values : ', response);
				}
			})
			.catch(function (reason) {
				console.warn('Error changing data ', reason)
			});
```
