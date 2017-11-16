===========================
PMC Checking Tool (CheeTah)
===========================

PMC Checking Tool (CheeTah) is designed to simplify and speed up checking of the articles for PMC process.

The goal of the tool is to mark up everything which is correct and attempt to pin point incorrect entries.
Generally everything marked in Green is OK and EVERYTHING ELSE needs to be checked manually. Even though tool marks certain entries in Amber or Blue, it does not mean that those are the only issues of the paper. There can be others not found by the tool. Those should be checked manually.

.. NOTE::
	
	Even though every attempt is made to make sure that only valid entries are marked in green, occasionally tool may fail to identify wrong entries and mark them green.
	If you notice such cases, please report them to Lisa via email.

Download
--------

You can download CheeTah `here`_.


Interface
---------

CheeTah tool interface is depicted below.


.. image:: /_static/cheetah_interface.png
   :scale: 50%
   :alt: CheeTah Interface


You can use CheeTah to navigate to pii HTML page directly. No more copy/paste in the URL of other article and clicking on "HTML". 
You just need to paste pii in "Enter PII here" field and press "Go". Article will open in a new tab.

Once you have article page on your screen you can run the check by pressing "Run" button. |br|
If you need to get back to the "normal" page view, click on "Refresh" button in Chrome.



Functionality
-------------

**Legend:**

Green = OK |br|
Amber = likely an issue - check manually |br|
Blue = CheeTah was not able to parse this entry - check manually |br|

In references: |br|
Red = CheeTah was not able to count number of authors in the reference - check manually |br|
Yellow = CheeTah attempted to find and mark titles of in-house journals


CheeTah is cheeking different parts of the paper in accordance with PMC Standards. Information about each section you can find below.

1. Article Title
	CheeTah checks spelling and underlines (red dashed line) suspicious words.

2. Affiliations
	CheeTah checks spelling and underlines (red dashed line) suspicious words.

3. Correspondence to:
	CheeTah tries to match name(s) of author(s) in "Correspondence to:" section with list of authors in front matter. 
	If tool finds matching names, it highlights them in green, otherwise it highlights name(s) in amber.

4. Keywords
	CheeTah checks number of keywords in "Keywords" section.
	If number equals or is smaller than 5, it injects a message in dark blue - "number of keywords is OK".
	Otherwise, it injects error message trying to provide details about the issue.

	CheeTah also checks whether article has "Special Section" keywords (in this case it caters for 5 words + special sections words)

5. Received, Accepted, Published dates
	CheeTah checks the spelling and validates the dates.
	If date is correct, it marks it in green. Otherwise it highlights it in amber.

	It also checks whether Received date is smaller than Accepted date and Accepted date is smaller than Published date.
	If everything is correct, dates are marked in green. Otherwise in amber.

6. Callouts vs references
	CheeTah tries to match callouts with references.
	If there is a full match, the tool injects a message that number of missing callouts and references equals to zero.
	Otherwise, it injects a message with numbers of missed callouts and/or references.

7. References
	CheeTah checks "Author List" for all references (both of in-house and other journals).

	If CheeTah is able to find and validate all names of authors then it marks full author list in green.
	If CheeTah finds an issue in author name(s) it marks that name(s) in amber.

	If CheeTah is able to count names of authors and verify that that number is OK, then it marks **reference number** in green.
	If CheeTah is not able to count names of authors, then it marks **reference number** in red.

	CheeTah checks "Citation Data" for in-house journals only (Oncotarget, Aging, Genes and Cancer, Oncoscience)
	It tries to find in-house journal name and if CheeTah finds it, it checks the format of citation data (year, volume, pages. DOI)

	If citation data format is OK and correct DOI is present, CheeTah marks citation data in green.
	Otherwise it does not mark citation data in any color at all.

	Tool also tries to match names of in-house journals. For Oncotarget and Oncosience it ties to find "ocnotarget" and "ocnoscience".
	For Aging (Albany NY) it tries to find "aging" word. For Genes Cancer it tries to find "genes cancer, genescancer, genes&cancer, genes &cancer, genes& cancer, genes & cancer, genesandcancer, genesand cancer, genes andcancer, genes and cancer" words. The search for words is case insensitive.

	If any of those words are fond in reference, tool marks them in yellow.

	If you find words marked in yellow, pay close attention to the reference, as it can be incorrectly formatted reference for in-house journal.


.. |br| raw:: html

   <br />


.. _here: https://chrome.google.com/webstore/detail/pmc-checking-tool-cheetah/jppbbnoakdbbbdpcheegicopijmhkbek?authuser=0

