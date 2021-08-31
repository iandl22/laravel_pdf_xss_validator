# laravel_pdf_xss_validator
A simple validation rule to prevent PDF's being uploaded with XSS payloads

During a recent pentest I had an issue flagged where the tester could upload a pdf with javascript in it. While this wouldnt really be a problem if opened locally modern browsers often open them with built in viewer which allows the javascript to be executed.

![Screen Shot 2021-08-31 at 12 30 48](https://user-images.githubusercontent.com/55628650/131495811-2e245796-f70d-419a-b111-14937c299941.png)

After some googling to find out the best way to mediate the issue in Laravel I didn't find much so I wrote my own rule for it and thought I would share it.

It's a basic Laravel rule so you should be able to drop it directly into your app/Rules folder and it can be used like so 
`$request->validate(['the_file' => ['required', 'file', new PdfXssRule()]]);`



