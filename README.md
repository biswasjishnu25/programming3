# ---------------------------------------- prac 9 list , lay name, export png------------------------------------
# import arcpy
#
# pro =  r"C:\Users\anike\Downloads\Assignment_9_ProProject\Assignment_9_ProProject\MyProject.aprx"
#
# my_project = arcpy.mp.ArcGISProject(pro)
#
# maps_list = my_project.listMaps()
#
# for map in maps_list:
#     if map.name == "Wilson_Map":
#         lyr_lst = map.listLayers()
#         for lyr in lyr_lst:
#            print(lyr.name)
import os.path

import arcpy.management

# -----------------------------------------------------------------------------------------------

# import arcpy
#
# pro = r"C:\Users\anike\Downloads\Assignment_9_ProProject\Assignment_9_ProProject\MyProject.aprx"
#
# my_project = arcpy.mp.ArcGISProject(pro)
#
# layout_list = my_project.listLayouts()
#
# for lay in layout_list:
#     print(lay.name)

# ------------------------------------------------------------------------------------------------
# import arcpy
#
# pro = r"C:\Users\anike\Downloads\Assignment_9_ProProject\Assignment_9_ProProject\MyProject.aprx"
#
# my_project = arcpy.mp.ArcGISProject(pro)
#
# layout_list = my_project.listLayouts()
#
# for lay in layout_list:
#     if lay.name == "Aniket_map":
#         out = r"C:\Users\anike\Downloads\Assignment_9_ProProject\Assignment_9_ProProject"
#
#         lay.exportToPNG(out)
# print("completed")

# ------------------------------------------prac 7 pt,line, poly-------------------------------------------------------------

# import arcpy
# import os
#
# pro = r"C:\Users\anike\Downloads\Assignment_9_ProProject\Assignment_9_ProProject\MyProject.gdb"
#
# x = 75.85028442509994
# y = 22.701307651940358
#
# pt = arcpy.Point(x,y)
# ref = arcpy.SpatialReference("WGS 1984")
#
# PT = arcpy.PointGeometry(pt, ref)
#
# n = "indore"
# gpath = os.path.join(pro, n)
# arcpy.CopyFeatures_management(PT, gpath)
# print("complete")

# --------------------------------------------------------------------------------------------
# import os
# import arcpy
#
#
# pro = r"C:\Users\anike\Downloads\Assignment_9_ProProject\Assignment_9_ProProject\MyProject.aprx"
#
# name = "up to indore"
# p = os.path.join(pro, name)
#
# ix = 75.85028442509994
# iy = 22.701307651940358
#
# ux = 79.85778557885828
# uy = 27.622628298306687
#
# inpt = arcpy.Point(ix, iy)
# uppt = arcpy.Point(ux, uy)
#
# ref = arcpy.SpatialReference("WGS 1984")
#
# polyline = arcpy.Array()
#
# polyline.add(inpt)
# polyline.add(uppt)
#
# p_geom = arcpy.Polyline(polyline, ref)
# arcpy.CopyFeatures_management(p_geom, p)
# print("c")

# -----------------------------------------------------------------------------------------
# import os
# import arcpy
#
#
# pro = r"C:\Users\anike\Downloads\Assignment_9_ProProject\Assignment_9_ProProject\MyProject.gdb"
#
# name = "up to indore to kashmir"
# p = os.path.join(pro, name)
#
# ix = 75.85028442509994
# iy = 22.701307651940358
#
# ux = 79.85778557885828
# uy = 27.622628298306687
#
# kx = 74.8852720283263
# ky = 32.667842533929765
#
# ptin = arcpy.Point(ix, iy)
# ptup = arcpy.Point(ux, uy)
# kpt = arcpy.Point(kx, ky)
#
# ref = arcpy.SpatialReference("WGS 1984")
#
# polygon = arcpy.Array()
#
# polygon.add(ptin)
# polygon.add(ptup)
# polygon.add(kpt)
#
# pgeom = arcpy.Polygon(polygon, ref)
# arcpy.CopyFeatures_management(pgeom, pro)
# print("c")

# ======================================= pract 5,6 Search, x,y coord ============================================
# import  arcpy
# import  os
# path = r"C:\Users\anike\Downloads\ProProject_Cursors (2)\ProProject_Cursors\ProProject_Cursors.gdb"
# name = "MajorAttractions"
# pt = os.path.join(path, name)
#
# list = ["NAME", "ADDR"]
# with arcpy.da.SearchCursor(pt,list) as s_c:
#     for row in s_c:
#         print(row[0], row[1])
# print("c")

# -------------------------------------------------------------------------
# import  arcpy
# import  os
# path = r"C:\Users\anike\Downloads\ProProject_Cursors (2)\ProProject_Cursors\ProProject_Cursors.gdb"
# name = "MajorAttractions"
# pt = os.path.join(path, name)
#
# list = ["ESTAB", "NAME"]
#
# MA_after_1970 = []
# with arcpy.da.SearchCursor(pt,list) as s_c:
#     for row in s_c:
#         estab = row[0]
#         if estab > 1970:
#             MA_after_1970.append(row[1])
#
# for name in MA_after_1970:
#     print(name)
#
# print("c")

# ----------------------------------------------------------------------

# import arcpy
# import os
#
# path = r"C:\Users\anike\Downloads\ProProject_Cursors (2)\ProProject_Cursors\ProProject_Cursors.gdb"
# name = "MajorAttractions"
# pt = os.path.join(path, name)
#
# list = ["SHAPE@X", "SHAPE@Y"]
#
# with arcpy.da.SearchCursor(pt, list) as s_cur:
#     for row in  s_cur:
#         xcor = row[0]
#         ycor = row[1]
#         print(xcor, ycor)
#
# print("c")

# -------------------------------------- PRAC 5 update and insert cursor ---------------------------------------
# import  arcpy
# import  os
# path = r"C:\Users\anike\Downloads\ProProject_Cursors (2)\ProProject_Cursors\ProProject_Cursors.gdb"
# name = "MajorAttractions"
# pt = os.path.join(path, name)
#
# list = ["NAME", "ESTAB", "NAME"]
#
# with arcpy.da.UpdateCursor(pt, list) as u_cur:
#     for row in u_cur:
#
#         if row[1]<1960:
#             row[2] = "yes"
#
#         else:
#             row[2] = "no"
#             u_cur.updateRow(row)
#
# print("c")

# -------------------------------------------------------------------------------

# import arcpy
# import os
#
# gdp_path = r"C:\Users\anike\Downloads\ProProject_Cursors (2)\ProProject_Cursors\ProProject_Cursors.gdb"
# fc_name = "MajorAttractions"
#
# fc_path = os.path.join(gdp_path,fc_name)
#
# field_list = ["NAME","ESTAB","ADDR","CITYNM","ZIP","EMP","ACRES"]
#
# record_1 = (" Five Star Restaurant",2021,"841 STREET","SAN DIEGO",92101,150,10)
# record_2 = (" New Town Restaurant ",2022,"842 STREET","SAN DIEGO",92105,140,15)
#
# i_cursor = arcpy.da.InsertCursor(fc_path, field_list)
# i_cursor.insertRow(record_1)
# i_cursor.insertRow(record_2)
# print("Process Completed")


# -------------------------------------- PRAC 4 ------------------------------------------

# path = r"D:\Sem 3\Prog_3\P_4\ProProject_Selections\ProProject_Selections.gdb"
# name = "Wilson_Restaurants"
#
# j = os.path.join(path, name)
#
# arcpy.management.MakeFeatureLayer(j, "res_lyr")
# pre_count = arcpy.GetCount_management("res_lyr")
# print(pre_count)

# ---------------------------------------------------------------------------
# gdb_path = r"D:\1_BVIEER\3rd_sem\Programming for GIS- III Mr. Ronit Jadhav\Practical_4\Given_data\ProProject_Selections\ProProject_Selections.gdb"
# restaurant_fc_name = "Wilson_Restaurants"
# crime_fc_name = "Wilson_Crimes96"
#
# restaurant_fc_path = os.path.join(gdb_path,restaurant_fc_name)
# crime_fc_path = os.path.join(gdb_path,crime_fc_name)
#
# arcpy.management.MakeFeatureLayer(restaurant_fc_path,"restaurant_lyr")
# arcpy.management.MakeFeatureLayer(crime_fc_path,"crime_lyr")
#
# # getting count of all the features before selection
# pre_count1=arcpy.GetCount_management("restaurant_lyr")
# pre_count3=arcpy.GetCount_management("crime_lyr")
#
# # Query
# arcpy.management.SelectLayerByLocation("crime_lyr","WITHIN_A_DISTANCE","restaurant_lyr","500 meters")
# post_count3 =arcpy.GetCount_management("crime_lyr")
# print('crime near 500 meters of restaurant = {}'.format(post_count3))
#
# print("Process Completed")

# --------------------------------------------------------------------------------
# gdb_path = r"D:\1_BVIEER\3rd_sem\Programming for GIS- III Mr. Ronit Jadhav\Practical_4\Given_data\ProProject_Selections\ProProject_Selections.gdb"
# restaurant_fc_name = "Wilson_Restaurants"
# histdist_fc_name = "Wilson_Histdist"
# crime_fc_name = "Wilson_Crimes96"
#
# restaurant_fc_path = os.path.join(gdb_path,restaurant_fc_name)
# histdist_fc_path = os.path.join(gdb_path,histdist_fc_name)
# crime_fc_path = os.path.join(gdb_path,crime_fc_name)
#
# arcpy.management.MakeFeatureLayer(restaurant_fc_path,"restaurant_lyr")
# arcpy.management.MakeFeatureLayer(histdist_fc_path,"histdist_lyr")
# arcpy.management.MakeFeatureLayer(crime_fc_path,"crime_lyr")
#
# # getting count of all the features before selection
# pre_count1=arcpy.GetCount_management("restaurant_lyr")
# pre_count2=arcpy.GetCount_management("histdist_lyr")
# pre_count3=arcpy.GetCount_management("crime_lyr")
#
# print('Total Restaurants before selection = {}'.format(pre_count1[0]))
# print('Total historic district before selection = {}'.format(pre_count2[0]))
# print('Total crime before selection = {}'.format(pre_count3[0]))
#
# arcpy.management.SelectLayerByAttribute("restaurant_lyr","NEW_SELECTION","ALCOHOL=1")
# post_count1 = arcpy.GetCount_management("restaurant_lyr")
# print('total restaurants serves alcohol = {}'.format(post_count1))
#
# arcpy.management.SelectLayerByLocation("restaurant_lyr","WITHIN_A_DISTANCE","histdist_lyr","1000 feet","SUBSET_SELECTION")
# post_count2 =arcpy.GetCount_management("restaurant_lyr")
# print('total restaurants serves alcohol within 1000 feet of histdist = {}'.format(post_count2))
#
# arcpy.management.SelectLayerByLocation("crime_lyr","WITHIN_A_DISTANCE","restaurant_lyr","500 feet")
# post_count3 =arcpy.GetCount_management("crime_lyr")
# print('crime near 500 feet of restaurant = {}'.format(post_count3))
#
# arcpy.management.SelectLayerByAttribute("crime_lyr","SUBSET_SELECTION","ALCOHOL>0")
# post_count4 = arcpy.GetCount_management("crime_lyr")
# print('Alcohol related crime = {}'.format(post_count4))

#--------------------------------------------------Prac_3  Buffer  and text file ---------------------------------------------------#
# import arcpy
# import os
#
# arcpy.env.workspace = r"D:\Sem 3\Prog_3\assign_3\ProProject_AutomatingUsingLists\ProProject_AutomatingUsingLists.gdb"
#
# output_folder_path = r"D:\Sem 3\Prog_3\assign_3"
#
# output_text_file = "MajorAttractions_info.txt"
#
# output_file_path = os.path.join(output_folder_path, output_text_file)
#
# print(output_file_path)
#
# file_obj = open(output_file_path, "w")
#
# fc_list = arcpy.ListFeatureClasses("MajorAttractions")
#
# for fc_name in fc_list:
#     print(fc_name)
#
# print("--------------------------------")
#
# field_list = arcpy.ListFields("MajorAttractions")
# for field in field_list:
#     print("Field Name: {},  Type: {}, Length: {}".format(field.name, field.type, field.length))
#     file_obj.write("Name: {}, Type: {}, Length: {} \n".format(field.name, field.type, field.length))
#
#     print("--------------------------")
#     file_obj.write("-------------------------------\n")
# file_obj.close()
# print("Process Completed")
# --------------------------------------------------------------------------------------------------------

# import arcpy
#
# arcpy.env.workspace = r"D:\Sem 3\Prog_3\assign_3\ProProject_AutomatingUsingLists\ProProject_AutomatingUsingLists.gdb"
#
# feature_class_list = arcpy.ListFeatureClasses()
# print(feature_class_list)
#
# for fc in feature_class_list:
#     desc_obj = arcpy.Describe(fc)
#     shape_type = desc_obj.shapeType
#
#     if shape_type == "Point":
#         buffer_distance = "400 feet"
#     elif shape_type == "Polyline":
#         buffer_distance = "1500 feet"
#     elif shape_type == "Polygon":
#         buffer_distance = "800 feet"
#
#     Output_buffer = fc + "_Buffer"
#     arcpy.analysis.Buffer(fc, Output_buffer, buffer_distance)
#
# print("process complete")
#-------------------------------------prac 2 Pop/Append-------------------------------------------------------------------------
# # Declare a list variable
# cities = ["Mumbai", "Thane","Kurla", "Malad", "Nashik"]
# print(cities)
# #  Print the length of the list
# print(len(cities))
#
# # Append a new city to the existing list
# cities.append("Ghatkopar")
# print(cities)
# #  Print the length of the list
# print(len(cities))
#
# # Remove an element at index '2’ from the list and print
# cities.pop(2)
# print(cities)
# print("Process_Completed")

# # Printing Country Names
# countries_and_capitals = {"India": "Delhi", "USA": "Washington_DC", "Japan": "Tokyo", "Australia": "Canberra"}
# print("Countries_Name:")
# for Countries in countries_and_capitals.keys():
#     print(Countries)
#
# # Inserting One Country and its Capital
# new_country = "Italy"
# new_capital = "Rome"
#
# countries_and_capitals[new_country] = new_capital
# print(countries_and_capitals)
#
# # Print the length of the dictionary
# print(len(countries_and_capitals))
#
# # # Remove an element from the dictionary
# countries_and_capitals.pop("USA")
# print(countries_and_capitals)
# print("Process Completed")

# Task 2
# import arcpy
# import os
#
# file_GDB_path = r"D:\Sem 3\programming for GIS 2\Assignment_2\ProProject_Practical_Two\ProProject_Practical_Two\World_data.gdb"
# fc_name = ["lakes"]
#
# for fc in fc_name:
#     fc_path = os.path.join(file_GDB_path, fc)
#     desc_obj = arcpy.Describe(fc_path)
#
#     sr_obj = desc_obj.spatialReference
#     print(sr_obj.name)
#     print(sr_obj.type)
#
# shape_type = desc_obj.shapeType
# print("The geometry type of feature class: {} is {}".format(fc, shape_type))
#
# field_list = desc_obj.fields
# for field in field_list:
#         print("The field name is {} and the type is {}".format(field.name,field.type))

# Task 3
# import arcpy
#
# raster_path = r"C:\Users\anike\Downloads\ProProject_Practical_Two\ProProject_Practical_Two\RASTER_DATA\erelev"
# desc_obj = arcpy.Describe(raster_path)
# print(desc_obj.bandCount)
#
# print(desc_obj.format)
#
# print(desc_obj.height)
# print(desc_obj.width)
# print(desc_obj.basename)
# print("Process Completed")

# -------------------------------------------------------------Prac 1 arthematic/ Buffer
# # 👉🏼👉🏼 Task 1: Declare two numeric variables and perform arithmetic operations like addition,
# number_1 = 45
# number_2 = 63
#
# # performing arithmetic operations like addition, subtraction, multiplication and division
# addition = (number_1 + number_2)
# subtraction = (number_1 - number_2)
# multiplication = (number_1 * number_2)
# division = (number_1/number_2)
#
# print('addition = {}'.format(addition))
# print('subtraction = {}'.format(subtraction))
# print('multiplication = {}'.format(multiplication))
# print('division = {}'.format(division))
# print("Process Completed")
#------------------------------------------loop----------------------------------------------------------
# Task 2: Loop through a list of five integers and print the integer only if it is greater than 50.
# Create a list
# number_list = [98, 49, 58, 100, 10, 5, 60, 53, 70, 35, 25, 45]
# print("printing all integer ")
# for l in number_list:
#     print(l)
#
# print("printing the integer only if it is greater than 50")
# for y in number_list:
#     if y > 50:
#         print(y)
# ----------------------------------------Buffer--------------------------------------------------------------------
# Task 3: Creating Buffers:
# a. Create a 500-meter buffer using the Python window
# b. Create 1000, 1200, and 1400 feet buffers in a single Python script using an IDE and verify the results in ArcGIS Pro
# """
#
# # Create a 500-meter buffer using the Python window **************************************************
#
# # Import arcpy package
# import arcpy
#
#
# # Setting the default workspace
# # arcpy.env.workspace = r"D:\1_BVIEER\3rd_sem\Programming for GIS- III Mr. Ronit Jadhav\Assignments\Assignment_1\ProProject_Practical_One\Practical_One.gdb"
#
# # Corrected usage of arcpy.analysis.Buffer
# # arcpy.analysis.Buffer("Wilson_Schools", "Wilson_School_Buffer_500m", "500 Meters")
# # print("Process Completed")
#
# # ****************************************************************************************
# # Create 1000, 1200, and 1400 feet buffers in a single Python script using an IDE and verify the results in ArcGIS Pro
# # *****************************************************************************************
#
# # # Setting the default workspace
# # arcpy.env.workspace = r"D:\1_BVIEER\3rd_sem\Programming for GIS- III Mr. Ronit Jadhav\Assignments\Assignment_1\ProProject_Practical_One\Practical_One.gdb"
# #
# # # Create 1000 feet buffer
# # arcpy.analysis.Buffer("Wilson_Schools", "Wilson_School_Buffer_1000ft", "1000 Feet")
# #
# # # Create 1200 feet buffer
# # arcpy.analysis.Buffer("Wilson_Schools", "Wilson_School_Buffer_1200ft", "1200 Feet")
# #
# # # Create 1400 feet buffer
# # arcpy.analysis.Buffer("Wilson_Schools", "Wilson_School_Buffer_1400ft", "1400 Feet")
# #
# # print("Process Completed")
#-----------------------------------------------------------------------------------------------------------------------
# Task 4: Use Arcpy. management.FeatureToPoint to convert Wilson_Zoning
#       polygon feature class into a point feature class using an IDE and verify the results in ArcGIS Pro
# '''
# # Import arcpy package
# import arcpy
#
# # Setting the default workspace
# Wilson_Zoning_path = r"D:\1_BVIEER\3rd_sem\Programming for GIS- III Mr. Ronit Jadhav\Assignments\Assignment_1\ProProject_Practical_One\Practical_One.gdb\Wilson_Zoning"
#
# # Create point features at the centroids of polygons
# wilson_polygon = Wilson_Zoning_path + "_PolygonToPoint"
# arcpy.management.FeatureToPoint(Wilson_Zoning_path, wilson_polygon )
#
# print("Process Completed")
#
##-----------------------------------------------------------------Jupyter---------------------------------------------------------------------------
#!/usr/bin/env python
# coding: utf-8

# In[1]:

#
# a = 5
# b = 7
#
#
# # In[2]:
#
#
# add = a+b
# sub = a-b
#
#
# # In[5]:
#
#
# print(add,sub)
#
#
# # In[6]:
#
#
# color = ['blue','green','red','pink']
#
#
# # In[7]:
#
#
# print(color[2])
#
#
# # In[9]:
#
#
# india = {'maha':'mum', 'mp':'bhop','bihar':'patna'}
#
#
# # In[10]:
#
#
# print(india)
#
#
# # In[12]:
#
#
# for states in india:
#  print('{} capital is {}'.format(states,india[states]))
#
#
# # In[15]:
#
#
# import arcgis
# my_gis = arcgis.GIS("https://www.arcgis.com","Aniket_Dalvi","Soloan_25")
# my_gis
#
#
# # In[16]:
#
#
# my_gis.content.search(query = "title: trip")
#
#
# # In[21]:
#
#
# my_gis.content.search("owner: 09ranojipatil_BVIEER", max_items = 100, item_type = 'WEB MAP')
#
#
# # In[22]:
#
#
# my_gis.users.search()
#
#
# # In[26]:
#
#
# pub = my_gis.content.get("391caf794d2f46898d4f23493d1bdb00")
# pub
#
#
# # In[28]:
#
#
# pub_lyr = pub.layers[0]
# pub_lyr
#
#
# # In[29]:
#
#
# pub_lyr.properties.capabilities
#
#
# # In[33]:
#
#
# for field in pub_lyr.properties.fields:
#     print(f":Field Name: {field['name']}")
#     print(f"Field Type: {field['type']}")
#     print("------------------------------------")
#
#
# # In[34]:
#
#
# qry = pub_lyr.query(where = "MOUNT_TYPE = 'yoke'")
# qry.sdf
#
#
# # In[ ]:
