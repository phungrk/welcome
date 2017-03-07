# Tool, Software

## Mac:

1. Source tree :[Homepage](https://www.sourcetreeapp.com/) | [RIV Dev wiki](https://github.com/riv-dev/git/wiki)
2. DiffMerge: [Homepage](https://sourcegear.com/diffmerge/) | [RIV Dev wiki](https://github.com/riv-dev/git/wiki/How-to-resolve-conflicts)
3. Visual Studio Code: [Homepage](https://code.visualstudio.com/) | [RIV Dev wiki](https://github.com/riv-dev/Visual-Studio-Code/wiki)
4. Japanese: [RIV Dev wiki](https://github.com/riv-dev/Japanese-font-families)
5. Photoshop: [Homepage](http://www.photoshop.com/) | [RIV Dev wiki](https://github.com/riv-dev/photoshop/wiki)
6. Dropbox: [Homepage](https://www.dropbox.com)
7. AMPPS: [Homepage](http://www.ampps.com/) | [RIV Dev wiki](https://github.com/riv-dev/ampps/wiki)
8. Vagrant: [Homepage](https://www.vagrantup.com/)
8. Testing
    - VirtualBox: [Homepage](https://www.virtualbox.org/wiki/Downloads)
    - GenyMotion: [Homepage](https://www.genymotion.com/) | [Hướng dẫn sử dụng](https://github.com/riv-dev/welcome/wiki/_genymotion)
    - IE: [Free Virtual Machine](https://developer.microsoft.com/en-us/microsoft-edge/tools/vms/)
    - [Install Window Virtual Machine with VirtualBox](https://drive.google.com/drive/u/0/folders/0B2x6OMK4si7seWRfcDg0RkQ4Vjg)
    
    
## Chrome extensions: 

1. [Page ruler](https://chrome.google.com/webstore/detail/page-ruler/jlpkojjdgbllmedoapgfodplfhcbnbpn)
2. [Dimensions](https://chrome.google.com/webstore/detail/dimensions/baocaagndhipibgklemoalmkljaimfdj)
3. [Pesticide for Chrome](https://chrome.google.com/webstore/detail/pesticide-for-chrome/bblbgcheenepgnnajgfpiicnbbdmmooh)
4. [PerfectPixel](https://chrome.google.com/webstore/detail/perfectpixel-by-welldonec/dkaagdgjmgdmbnecmcefdhjekcoceebi?hl=en)

## Project Environment 

1. [Install Node.js](https://github.com/riv-dev/nodejs/wiki/Install-Nodejs)
2. Install `grunt-cli`: `npm i grunt-cli -g`
3. Install `bundle`: `sudo gem install bundle`
4. Project environment preparation. 

```
1. cd PATH/TO/PROJECT/../_dev
2. npm i
3. bundle i
4. grunt 
```

# Knowleages 

## Some coding rules:
Coding rule 

1. Add `@charset "utf-8";` at the first of file. (To avoid mojibake error with Japanese when compile files on Windows environment ). You can use [file template](https://github.com/riv-dev/Visual-Studio-Code/wiki/file-template) to so this problem automatically when add new file.
2. Use `min-width` instead of `max-width` as breakpoint.
3. Use `px` for `font-size`,don't use `em, rem, %...` , because it offers absolute control over text.
4. Use `em` for `line-height`, because em can change dynamically with the font in use.
5. Hover: is default apply for `Link`, `Button` on PC even if have no hover guide for this. 


	 ```css 
	    .xyz {
	        @media(min-width: $screen-md-min) {
	            @include transition(0.2s);
	            &:hover {
	                ...
	            }
	        }
	    }
	 ```
	 
	 - If `text` link: 
	 
	 ```css 
	    .xyz {
	        @media(min-width: $screen-md-min) {
	            @include transition(0.2s);
	            &:hover {
	                text-decoration: underline; 
	                //or 
	                text-decoration: none;
	            }
	        }
	    }
	 ```
	 - If `img` link: 
	 
	 ```css
	    .xyz {
	        @media(min-width: $screen-md-min) {
	            @include transition(0.2s);
	            &:hover {
	                @include opacity(0.8);
	            }
	        }
	    }
	 ```
	 - If `button`:
 
	 ```css
	    .xyz {
	        @media(min-width: $screen-md-min) {
	            @include transition(0.2s);
	            &:hover {
	               @include opacity(0.8);
	               //or
	               // invert background color.
	            }
	        }
	    }
	   ```



6. Button 
   Don't fixed padding left, right for button.
   Do padding left, right 10px. 
 
 ![button coding rule](https://github.com/riv-dev/welcome/blob/master/images/button.png)

7. Instead of styling a specific `tag`, create and apply a class that describes the `tag`. 

 Don't:
 
 ```	
   .map__list li {
		color:red;	
   }
 ```
 
 Do: Create class for li, then make style for that class.
 
 ```
 	.map__list map__item {
		color:red;
	}
 ```
	
	
 Ref: [Two Main Principles of OOCSS](https://github.com/stubbornella/oocss/wiki#two-main-principles-of-oocss)
 
8. Use `small` tag for Copyright:

 ```
 <small>Copyright (C) Okinawa Beach Soccer Camp</small>
 ```

9. Heading tag

 ![](https://dab1nmslvvntp.cloudfront.net/wp-content/uploads/2014/09/1409729849headings-1-6.png)

 will have Document Outline:

 ![Heading Tag](https://dab1nmslvvntp.cloudfront.net/wp-content/uploads/2014/09/1409729864heading-document-outline.png)

 We usually use `h1` for `logo`, `page title`.
	
10. Don't use `flexbox`, `calc` because of old version of IE, Android is not supported.
11. Think about if add/remove elements will effect layout while coding. For example,thinking about if text is added make paragraph more longer, if elements is removed/added...  make margin between elements become ugly ?...
12. Use `js-` prefixed class names for selector that need `javascript` code. Never reference js- prefixed class names from CSS files. `js-` are used exclusively from JS files.
13. Use root path, don't use relative path unless you have a specific reason.
 ```
 <img src="/common/images/image.jpg">

 .example {
  background-image: url("/common/images/pages/top/_bg_sp.jpg");
 }
 ```
14. Use absolute path for meta `og:image`

```
 <meta property="og:image" content="http://domain.com/common/images/_ogp_fb.jpg">
```
15. [Void Elements](https://www.w3.org/TR/html51/syntax.html#void-elements) only have a start tag; end tags must not be specified. For. ex Use `<br>`, `<img>`, `<meta>`, `<input>` ... Don't use `<br/>`, `<img src="" alt="" />`, ...
16. Add `<meta name="format-detection" content="telephone=no">` to `head`
17. Use compass mixins : https://github.com/riv-dev/compass/wiki/Common-Compass-Mixins

## Tech Talk checklist 

https://docs.google.com/spreadsheets/d/1ilke0kke4WzsWrf2jLqlG_5NDA_PpeCTnnTQJwrzJyg/edit#gid=0

## Frontend 

1. Sass: [Homepage](http://sass-lang.com/) | [RIV Dev wiki](https://github.com/riv-dev/sass)
2. Compass: [Homepage](http://compass-style.org/) | [RIV Dev wiki](https://github.com/riv-dev/compass)
3. HTML: [Homepage](https://www.w3.org/html/) | [RIV Dev wiki](https://github.com/riv-dev/html)
4. Handlebars: [Homepage](http://handlebarsjs.com/) | [RIV Dev wiki](https://github.com/riv-dev/handlebars)
5. Grunt: [Homepage](http://gruntjs.com/) | [RIV Dev wiki](https://github.com/riv-dev/grunt)
6. Gulp: [Homepage](http://gulpjs.com/) | [RIV Dev wiki](https://github.com/riv-dev/gulp)
7. Webpack: [Homepage](https://webpack.github.io/) | [RIV Dev wiki](https://github.com/riv-dev/webpack)
8. Nodejs: [Homepage](https://nodejs.org/en/)| [RIV Dev wiki](https://github.com/riv-dev/nodejs)

## Backend

## Mobile 

## VR 

## AI

...

If you click the link, you meet 404, it meen that waiting your contribute :smile: 

# Work

## Preparing workspace

Depend on your hoppy, but I think you should create at least 2 folders like below. (It make me easy to support you when you need my supporting :smile: 

1. Open terminal 
2. Create workspace: `mkdir workspace`
3. Get into workspace: `cd workspace`
4. Create `projects`folder for projects's source:  `mkdir projects` . Then [set this `projects` folder as the default when clone new project](https://github.com/riv-dev/git/wiki/Setting#general-setting)
5. Create `lab` folder for reseaching:     `mkdir lab`

## Email 

### Step 1
![mac mail add account](https://github.com/riv-dev/welcome/blob/master/images/mac-mail-add-account.png)

### Step 2

![mac mail google](https://github.com/riv-dev/welcome/blob/master/images/mac-mail-google.png)


### Step 3

![mac mail sign in](https://github.com/riv-dev/welcome/blob/master/images/mac-mail-sign-in.png)

## Mac useful shortkey 

Refs: https://support.apple.com/en-us/HT201236

### Key/mark table 

| Key       | Mark |
|-----------|------|
| Command   | ⌘    |
| Shift     | ⇧    |
| Option    | ⌥    |
| Control   | ⌃    |
| Caps Lock | ⇪    |

### 1. Quick open an app/file/folder: 
- `⌘+Space bar`
- Type app/file/folder name. You can type some word then Space to complete app name 
- `Enter` 

### 2. Switch app 

- `⌘+Tab`: forward 
- `⌘+⇧+Tab`:  backward

### 3. [Waiting your contribute ]




