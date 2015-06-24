##What are triggers?
A trigger is an instruction that the database should automatically execute a particular function whenever a specific operation is performed.

##Sample Trigger
	
	create trigger change_rate
	after update of rate on master
	for each row execute procedure rate_update();

##When
* before
* after
* instead of
This decides whether the procedure is executed before, after or instead of the operation.

##How many times
* for each row
* for each statement
This specifies whether the trigger procedure should be fired once for every row affected by the trigger event, or just once.

##Optional conditions

#### of
This specifies the column of the table which is being updated.

#### when
This specifies a particular condition upon which the trigger must execute

##PL/pgSQL
This language can be used in PostgreSQL to create functions, trigger procedures, loops etc.

##Sample function

	CREATE OR REPLACE FUNCTION master_trigger()RETURNS trigger AS $trig1$
		BEGIN
		if(tg_op = 'UPDATE') then
				update pricehist set vtill = current_date where pricehist.itemid = new.id and vtill ISNULL;
				insert into pricehist (itemid, price, vfrom) values (new.id, new.rate, current_date);
		elsif (tg_op = 'INSERT') then
				insert into pricehist (itemid,price,vfrom) values (new.id, new.rate, current_date);
		end if;
		return null;
		END;
		$trig1$ LANGUAGE plpgsql;

##Keywords used

* Create - THis creates the function
* Create or replace - This creates a function and replaces an old one with the same name(if such a function exist).
* () - The input parameters are specified here.
* Returns - The return type is specified after this keyword.
* Declare - All variables used are declared after this keyword.
* Begin - This specifies the beginning of operations in the function.
* Return - This statement returns a value from the function.
* End - This specifies the end of operations in the function.
* The function is usually written as a string constant with dollar quotes.


