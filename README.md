Current Version: 0.01-Alpha

This is an attempt to add multiple page management to TinyMCE4.

Currently the code is is EXPIREMENTAL. Use at your own risk.

At this point the pages are so far limited to dynamic.

Once I am done coding the basic stuff, I'll clean up the code and make it more presentable.

#### Requirements:

  jQuery 1.X+

  TinyMCE 4.X

#### Plugin name:

  pagemanager


#### Options:

  pm_section_def = A HASH/ASSOCIATED ARRAY that sets the definitions for the page types (HASH/ASSOCIAT)

     sub options: 
          text = Sets the text
	  class = Sets the class
          data-name = should generally match the text


  pm_section_order = Sets the nesting order of the page types
  
 

#### Commands:

  mcePMAddPage = Open Add Page Dialog
	Example: 
		editor.execCommand( 'mcePMAddPage', false, { type:'v' } );

  mcePMImportPage = Manually add page
	Example:
		editor.execCommand( 'mcePMImportPage', false, { headers: ['volume here','chapter here','part here'], type: 'v', content: 'Content Goes Here'   } )


#### Syntax:

```
  <script>  
  tinymce.init({  
    selector: "#mytextarea",  
    toolbar: 'undo redo | styleselect | bold italic | alignleft aligncenter alignright alignjustify | bullist numlist outdent indent',  
    height: 700,  
    plugins: ['pagemanager'],
    pm_section_def:{
	'v':{ text:'Volume', 'class':'np-header-volume', 'data-name':'Volume' },
	'c':{ text:'Chapter','class':'np-header-chapter', 'data-name':'Chapter' },
	'p':{ text:'Part', 'class':'np-header-part', 'data-name':'Part' }
    },
    pm_section_order:'vcp'
  
  });  
  </script>
```

#### Demo:

This demo uses this plugin via external_plugin hosted by github, which is not the recommended way to go, especially since github is not a cdn. Add the plugin to your plugins folder and include languagetool

  https://knowzero.github.io/tinymce4-pagemanager/demo.html

