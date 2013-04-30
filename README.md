Tesseract OCR iOS
=================

Tesseract OCR iOS is a static library compiled for iOS5+, compiled also for armv7s.
<br />
<br />
It will produces only two files:
libTesseract OCR iOS.a
Tesseract.h

Attach the project
=================

Add (drag&drop) the "Tesseract-OCR-iOS" XCode Project under your project
<br />
Import UIKit with: <code>#import &lt;UIKit/UIKit.h&gt;</code>
<br />
Import libTesseract OCR iOS with: <code>#import &lt;Tesseract OCR iOS/Tesseract.h&gt;</code> 
<br />
Use Tesseract class like explained here: https://github.com/ldiqual/tesseract-ios

ex. from https://github.com/ldiqual/tesseract-ios but using the <strong>"Tesseract-OCR-iOS" XCode Project</strong>
<pre><code>#import &lt;UIKit/UIKit.h&gt;
#import &lt;Tesseract OCR iOS/Tesseract.h&gt;

Tesseract* tesseract = [[Tesseract alloc] initWithDataPath:@"tessdata" language:@"<strong>grc</strong>"];
//language are used for recognition. Ex: grc. Tesseract will search for a grc.traineddata file in the dataPath directory. 
//grc.traineddata is already available in the libTesseract OCR iOS static library.

[tesseract setVariableValue:@"0123456789" forKey:@"tessedit_char_whitelist"];
[tesseract setImage:[UIImage imageNamed:@"image_sample.jpg"]];
[tesseract recognize];

NSLog(@"%@", [tesseract recognizedText]);
</code></pre>

<br />
Set Tesseract variable key to value. See http://www.sk-spell.sk.cx/tesseract-ocr-en-variables for a complete (but not up-to-date) list.
<br />
For instance, use tessedit_char_whitelist to restrict characters to a specific set.

License
=================

Tesseract OCR iOS (this repo) is under MIT License.
<br />
Tesseract-ios, powered by ldiqual https://github.com/ldiqual/tesseract-ios, is under MIT License.
<br />
Tesseract, powered by Google http://code.google.com/p/tesseract-ocr/, is under Apache License.

Thanks
=================

Thanks to ldiqual for the good wrapper for Tesseract.
