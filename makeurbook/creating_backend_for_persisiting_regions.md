-> managed to create cropRegions table
	changing schema lifecycle
		change model.py => orm.py => generates_tables.sql
		
-> now will create a service add_region(page_id, crop_ob)
	services.py -> entry_points/app.py