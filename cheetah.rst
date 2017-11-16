===========================
PMC Checking Tool (CheeTah)
===========================

PMC Checking Tool (CheeTah) is designed to simoplify and speed up checking of the artiles for PMC.

The goal of the tool is to mark up everything which is correct and attempt to point at incorrect entries.
Generally everything marked in Green is OK and EVERYTHING ELSE needs to be checked manually. Even though tool marks certain entries in Amber or Blue, it does not mean that those are the only issues of the paper. There can be others not found by the tool. Those should be checked manually.

.. NOTE::
	
	Even though every attempt is made to make sure that only valid entries are marked in green, occassionally tool may fail to identify wrong entries and will mark them green.
	If you notice such case, please report them to Lisa via email.

Download
--------

You can download CheeTah :ref:`here<cheetah_download>`.


Interface
---------

CheeTah tool interfance is depicted below.


.. image:: /_static/cheetah_interface.png
   :alt: CheeTah Interface


You can use CheeTah to navigate to pii HTML page directly. No more copy/paste in the URL of other article and clicking on "HTML"
You just need to paset pii in "Enter PII here" field and press "Go". Article will open in a new tab.

Once you have article page on your screen you can run the check by pressing "Run" button.
If you need to get back to the "normal" page view, click on "Refresh" button in Chrome.



Functionality
-------------

**Legend:**

Green = OK
Amber = likely an issue - check manually
Blue = tool was not able to parse this entry - check manually

In references:
Red = tool was not able to count number of authors in the reference - check manually
Yellow = attempt to find and mark titles of in-house journals


Tool is cheking different parts of the paper in accordance with PMC Standards. Information about each section you can find below.

1. Article Title
	Tool checks spelling and underlines (red dashed line) suspecious words

2. Affiliations
	Tool checks spelling and underlines (red dashed line) suspecious words

3. Correspondence to:
	Tool tries to match name(s) of author(s) in "Correspondence to:" section with list of authors in front matter. 
	If tool finds matching names, it highlights them in green, otherwise it highlights name(s) in amber

4. Keywords
	Tool cheks number of keywords in "Keywords" section.
	If number equals or is smaller than 5, it injects a message in dark blue "number of keywords is OK"
	Otherwise, it injects error message trying to provide details about the issue.

	Tool also checks whether article has "Special Section" keywords (in this case it caters for 5 words + special sections words)

5. Recived, Accepted, Published dates
	Tool checks the spelling and validates the date
	If date is correct, it marks it in green. Otherwise it highlights it in amber

	It also cheks whether Recieved date is smaller than Accepted date and Acceoted date is smaller than Published date.
	If everything is correct, dates are marked in green. Otherwise in amber.

6. Call outs vs references
	Tool tries to match callouts with references.
	If there is a full match, the tool injects a mesage that number of missing callouts and references equals to zero.
	Otherwise, it injects a message with numbers of missed callouts and/or references.

7. References
	Tool checks "Author List" for all references (both of in-house and othe journals).

	If tool is able to find and validate all names of authors then it marks full author list in green.
	If tool finds an issue in author name(s) it marks that name(s) in amber.

	If tool is able to count names of authors and verify that number is OK, then it marks **reference number** in green.
	If tool is not able to count names of authors, then it marks **reference number** in red

	Tool checks "Citation Data" for in-house jounrals only (Oncotarget, Aging, Gens and Cancer, Oncoscience)
	It tries to find in-house journal name and if it finds it, it checks the format of citation data (year, volume, pages. DOI)

	If citation data format is OK and correct DOI is present, it marks citation data in green
	Otherwise it does not mark citation data at all

	Tool also tries to match names of in-house journals. For Oncotarget and Oncosience it ties to find "ocnotarget" and "ocnoscience".
	For Aging (Albany NY) it tries to find "aging" word. For Genes Cancer it tries to find "genes cancer, genescancer, genes&cancer, genes &cancer, genes& cancer, genes & cancer, genesandcancer, genesand cancer, genes andcancer, genes and cancer" words.

	If any of those words are fond in reference, tool marks them in yellow.

	If you find words marked in yellow, pay close attention to the reference, as it can be incorrectly formatted reference for in-house journal.


.. _cheetah_download: https://chrome.google.com/webstore/detail/pmc-checking-tool-cheetah/jppbbnoakdbbbdpcheegicopijmhkbek?authuser=0