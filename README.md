#codeigniter-doctrine


CodeIgniter 2.x , Doctrine 2.x and Composer

I am guessing you have basic understanding on Composer and you have already installed codeigniter with composer. Check reference. 

##Step 1 : install doctrine

Add or update composer.json file with 
	
	{
    "require": {        
        "doctrine/orm": "2.2.2",
        "doctrine/common": "2.2.0",
        "doctrine/dbal": "2.2.1",
        "symfony/console": "2.x",
        "symfony/yaml": "2.x"
    }
	}

Update composer  
	
	php composer.phar update 


This will update all necessary files 


##Step 2:

Replace files and read joelverhagen's blog post from reference. You need not to copy or create any php file from that blogpost.
Just try understand what he is saying.

Include following files and run following commands as necessary from inside application folder in commandline.

This generates model file based from Entities : 

	$php doctrine-cli.php orm:generate-entities models

This creates proxy class 

	$php doctrine-cli.php orm:generate-proxies

This removes existing tables referenced in entities. Be careful never to run this in production. 
	
	$php doctrine-cli.php orm:schema-tool:drop --force

This creates tables from Entities: 
	
	$php doctrine-cli.php orm:schema-tool:create


##Common Issues I have faced

This helped me to fix the datatye enum not found issue
	http://wildlyinaccurate.com/doctrine-2-resolving-unknown-database-type-enum-requested


##Plans

Will try to make this work with HVMC.



##Reference: 
	
	http://philsturgeon.co.uk/blog/2012/05/composer-with-codeigniter
	http://www.joelverhagen.com/blog/2011/05/setting-up-codeigniter-2-with-doctrine-2-the-right-way/
