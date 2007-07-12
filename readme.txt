=== Plugin Name ===
Contributors: Naatan
Donate link: http://www.naatan.com/
Tags: mailing, mailing list, mail, notify, blog notifier
Requires at least: 2.x
Tested up to: 2.1
Stable tag: trunk

Adds mailing list functionality to wordpress

== Description ==

Adds mailing list functionality to wordpress, allows you to make and manage unlimited mailing lists, design the form however you want and it has a "new blog" notification feature, sending an e-mail to subscribers whenever you blog.

===========
1.02 UPDATE
===========

    * Fixed bug where subscribers received mails with all subscribers in the ‘to’ field.

===========
1.01 UPDATE
===========

   * Fixed blog notify where HTML tags did not show up correctly

If your updating just replace the old files with the new ones..

== Installation ==

   1. Upload “naatan_notifyme.php” to your plugins directory
   2. Upload "notifyme.php" to your wordpress root directory
   3. Enable the plugin in WP Plugin Management
   4. That’s it! Access it from the main admin bar

== Arbitrary section ==

There are several ways to use this plugin, below I will describe some of them

   Using the default form in pages
   *******************************

   Imagen you would have a maillist named "Page Updates",
   When your creating a new page you would add the following tag where you want the form to appear..

     [notifyme]Page Updates[/notifyme]

   This goes for all maillists, just add the tags with the name of the maillist inside them.


   Creating a form inside your templates
   *************************************

   When your creating a form inside regular templates there are several things you have to do, 

     - The method of the form should be "POST" and the action should always be: "notifyme.php" 
  
     - You should always include the following fields, be it as input box, selection, checkbox.. no matter.

       * maillistid
       * naatan_notifyme_name
       * naatan_notifyme_website
       * naatan_notifyme_email
       * submit_notifyme_subscribe  

       The maillistid is the ID of the mail list and should definitely be set, you can get your mail list ID
       from the main NotifyMe page, where the maillists are listed.

       naatan_notifyme_ - name / website / email.. I don't think I need to explain this

       submit_notifyme_subscribe is what the script uses to verify that the form has been submitted and 
       should always be set, preferrably in the form of a submit button.

       For some examples check further below


   Maillist Selection list 
   ***********************
   
   When your using the template method you can use a selection box to have the user select which maillist
   he wants to subscribe to.. this is usefull when you want to use something like a "Notify me of updates for.."
   section.
   Simply add the following in your template where you want to receive the option variables.. 

     <?php naatan_notifyme_maillistselect(); ?>

   Usage Example;

     <select name="maillistid">
       <?php naatan_notifyme_maillistselect(); ?>
     </select>

== A brief Markdown Example ==

TEMPLATE EXAMPLES

Standard Subscribe me Form:
***************************

	<h2>Subscribe</h2>
	<ul>
	  Subscribe to updates
	  <form name="notifymeForm" method="post" action="notifyme.php">
	    <input type="hidden" name="maillistid" value="1">
	    <input type="text" name="naatan_notifyme_name" value="Your Name" size="20" onClick="this.value='';" style="margin-top: 2px;"><br>
	    <input type="text" name="naatan_notifyme_email" value="E-Mail Address" size="20" onClick="this.value='';" style="margin-top: 2px;"><br>
	    <input type="text" name="naatan_notifyme_website" value="Website URL" size="20" onClick="this.value='';" style="margin-top: 2px;"><br>
	    <input type="submit" name="submit_notifyme_subscribe" value="Subscribe" style="margin-top: 2px;">
	  </form>
	</ul>


Subscribe me form with Maillist Selection
*****************************************

	<h2>Subscribe</h2>
	<ul>
	  Subscribe to updates for..
	  <form name="notifymeForm" method="post" action="notifyme.php">
	    <select name="maillistid">
	      <?php naatan_notifyme_maillistselect(); ?>
	    </select><br>
	    <input type="text" name="naatan_notifyme_name" value="Your Name" size="20" onClick="this.value='';" style="margin-top: 2px;"><br>
	    <input type="text" name="naatan_notifyme_email" value="E-Mail Address" size="20" onClick="this.value='';" style="margin-top: 2px;"><br>
	    <input type="text" name="naatan_notifyme_website" value="Website URL" size="20" onClick="this.value='';" style="margin-top: 2px;"><br>
	    <input type="submit" name="submit_notifyme_subscribe" value="Subscribe" style="margin-top: 2px;">
	  </form>
	</ul>


Form with only the E-Mail field required
****************************************

	<h2>Subscribe</h2>
	<ul>
	  Subscribe to updates
	  <form name="notifymeForm" method="post" action="notifyme.php">
	    <input type="hidden" name="maillistid" value="1">
	    <input type="hidden" name="naatan_notifyme_name" value="Subscriber"><br>
	    <input type="hidden" name="naatan_notifyme_website" value="Unspecified"><br>
	    <input type="text" name="naatan_notifyme_email" value="E-Mail Address" size="20" onClick="this.value='';" style="margin-top: 2px;"><br>
	    <input type="submit" name="submit_notifyme_subscribe" value="Subscribe" style="margin-top: 2px;">
	  </form>
	</ul>
