# programming3
Assignment 1: -
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

# *******************************************************************************
# 👉🏼👉🏼 Task 2: Loop through a list of five integers and print the integer only if it is greater than 50.
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

# *********************************************************************************
"""
👉🏼👉🏼 Task 3: Creating Buffers:
a. Create a 500-meter buffer using the Python window
b. Create 1000, 1200, and 1400 feet buffers in a single Python script using an IDE and verify the results in ArcGIS Pro
"""

# Create a 500-meter buffer using the Python window **************************************************

# Import arcpy package
import arcpy


# Setting the default workspace
# arcpy.env.workspace = r"D:\1_BVIEER\3rd_sem\Programming for GIS- III Mr. Ronit Jadhav\Assignments\Assignment_1\ProProject_Practical_One\Practical_One.gdb"

# Corrected usage of arcpy.analysis.Buffer
# arcpy.analysis.Buffer("Wilson_Schools", "Wilson_School_Buffer_500m", "500 Meters")
# print("Process Completed")

# ****************************************************************************************
# Create 1000, 1200, and 1400 feet buffers in a single Python script using an IDE and verify the results in ArcGIS Pro
# *****************************************************************************************

# # Setting the default workspace
# arcpy.env.workspace = r"D:\1_BVIEER\3rd_sem\Programming for GIS- III Mr. Ronit Jadhav\Assignments\Assignment_1\ProProject_Practical_One\Practical_One.gdb"
#
# # Create 1000 feet buffer
# arcpy.analysis.Buffer("Wilson_Schools", "Wilson_School_Buffer_1000ft", "1000 Feet")
#
# # Create 1200 feet buffer
# arcpy.analysis.Buffer("Wilson_Schools", "Wilson_School_Buffer_1200ft", "1200 Feet")
#
# # Create 1400 feet buffer
# arcpy.analysis.Buffer("Wilson_Schools", "Wilson_School_Buffer_1400ft", "1400 Feet")
#
# print("Process Completed")

# ======================================================================================================================
'''
👉🏼👉🏼 Task 4: Use Arcpy. management.FeatureToPoint to convert Wilson_Zoning 
      polygon feature class into a point feature class using an IDE and verify the results in ArcGIS Pro
'''
# Import arcpy package
import arcpy

# Setting the default workspace
Wilson_Zoning_path = r"D:\1_BVIEER\3rd_sem\Programming for GIS- III Mr. Ronit Jadhav\Assignments\Assignment_1\ProProject_Practical_One\Practical_One.gdb\Wilson_Zoning"

# Create point features at the centroids of polygons
wilson_polygon = Wilson_Zoning_path + "_PolygonToPoint"
arcpy.management.FeatureToPoint(Wilson_Zoning_path, wilson_polygon )

print("Process Completed")


Assignment 2: - 


import arcpy
import os

#  Question 1: What is the syntax for the describe tool? *********************************************************
# ****************************************************************************************************************

# # Specify the path to the feature class
# fc_path = r'D:\1_BVIEER\3rd_sem\Programming for GIS- III Mr. Ronit Jadhav\Assignments\Assignment_2\Data\ProProject_Practical_Two\World_data.gdb\Lakes'
#
# # Describe the feature class
# desc = arcpy.Describe(fc_path)
#
# # Access and print specific properties
# print(f"Feature Class Name: {desc.name}")
# print(f"Data Type: {desc.dataType}")
# print(f"Shape Type: {desc.shapeType}")

# Quistion 2: How can you obtain spatial reference name for a feature class? **************************************
# *****************************************************************************************************************

# # Specify the path to the feature class
# feature_path = r'D:\1_BVIEER\3rd_sem\Programming for GIS- III Mr. Ronit Jadhav\Assignments\Assignment_2\Data\ProProject_Practical_Two\World_data.gdb\Lakes'
#
# # Describe the feature class
# desc = arcpy.Describe(feature_path)
#
# # Access the spatial reference name
# spatial_reference_name = desc.spatialReference.name
#
# # Print the spatial reference name
# print("Spatial Reference Name: " + spatial_reference_name)

# ***********************************************Task 1*********************************************************
# Q1. Create a list object which contains name of different cities and perform the following operations on it:
# Q1.1. Append a new city to the existing list
# ----------------------------------------------------------------------------------------------------------------
# # Create a list of city names
# cities = ["Kolkata", "Delhi", "Mumbai", "Chennai", "Darjeeling"]
#
# # Append a new city to the list
# new_city = "Pune"
# cities.append(new_city)
#
# # Print the updated list
# print(cities)

# -----------------------------------------------------------------------------------------------------------------
# Q1.2. Print the length of the list
# -----------------------------------------------------------------------------------------------------------------
# # Create a list of city names
# cities = ["Kolkata", "Delhi", "Mumbai", "Chennai", "Darjeeling"]
#
# # Append a new city to the list
# new_city = "Pune"
# cities.append(new_city)
#
# # # Print the updated list
# print(cities)
#
# # Print the length of the list
# print("Length of the list:", len(cities))

# -----------------------------------------------------------------------------------------------------------------
# Q1.3. Remove an element at index '2’ from the list and print
# -----------------------------------------------------------------------------------------------------------------

# # Create a list of city names
# cities = ["Kolkata", "Delhi", "Mumbai", "Chennai", "Darjeeling"]
#
# # Remove the element at index 2 (third element)
# removed_city = cities.pop(2)
#
# # Print the updated list
# print("Updated list after removing element at index 2:")
# print(cities)
#
# # Print the removed city
# print("Removed city:", removed_city)

# ****************************************************************************************************************************************
# Q2. Create a dictionary object which contains country name as key and their capital as value and perform the following operations on it:
# Q2.1 Print only the name of countries (keys)
# ----------------------------------------------------------------------------------------------------------------------------------------
# # Create a dictionary of countries and capitals
# country_capital_dict = {
#     "India": "Delhi",
#     "Canada": "Ottawa",
#     "United Kingdom": "London",
#     "France": "Paris",
#     "Germany": "Berlin"
# }
#
# # Print only the names of countries (keys)
# country_names = list(country_capital_dict.keys())
# print("Names of Countries:")
# for country in country_names:
#     print(country)

# ----------------------------------------------------------------------------------------------------------------------
# Q2.2. Insert one more country and its capital
# ----------------------------------------------------------------------------------------------------------------------

# Existing dictionary of countries and capitals
# country_capital_dict = {
#     "India": "Delhi",
#     "Canada": "Ottawa",
#     "United Kingdom": "London",
#     "France": "Paris",
#     "Germany": "Berlin"
# }
#
# # Insert one more country and its capital
# new_country = "Italy"
# new_capital = "Rome"
# country_capital_dict[new_country] = new_capital
#
# # Print the updated dictionary
# country_names = list(country_capital_dict.keys())
# print("Names of Countries:")
# for country in country_names:
#     print(country)

# -----------------------------------------------------------------------------------------------------------------------
# Print the length of the dictionary
# -----------------------------------------------------------------------------------------------------------------------
# # Create a dictionary of countries and capitals
# country_capital_dict = {
#     "India": "Delhi",
#     "Canada": "Ottawa",
#     "United Kingdom": "London",
#     "France": "Paris",
#     "Germany": "Berlin"
# }
# # Print the length of the dictionary
# dictionary_length = len(country_capital_dict)
# print("Length of the Dictionary:", dictionary_length)

# -----------------------------------------------------------------------------------------------------------------------
# Remove an element from the dictionary
# -----------------------------------------------------------------------------------------------------------------------
# # Existing dictionary of countries and capitals
# country_capital_dict = {
#     "India": "Delhi",
#     "Canada": "Ottawa",
#     "United Kingdom": "London",
#     "France": "Paris",
#     "Germany": "Berlin"
# }
#
# # Remove a specific element by key
# remove = "Canada"
# if remove in country_capital_dict:
#     del country_capital_dict[remove]
#
#
# # Print the updated dictionary
# country_names = list(country_capital_dict.keys())
# print("Names of Countries:")
# for country in country_names:
#     print(country)

# ****************************************************************************************************************************
# Task 2: Describe the “Lakes” feature class from the world_data.gdb and print:
# a. Spatial reference
# ----------------------------------------------------------------------------------------------------------------------------

# # Specify the path to the feature class
# fc_path = r'D:\1_BVIEER\3rd_sem\Programming for GIS- III Mr. Ronit Jadhav\Assignments\Assignment_2\Data\ProProject_Practical_Two\World_data.gdb\Lakes'
#
# # Describe the feature class
# desc = arcpy.Describe(fc_path)
#
# # Access and print specific properties
# print(f"Spatial Reference Name: {desc.spatialReference.name}")

# -----------------------------------------------------------------------------------------------------------------------
# Feature type
# -----------------------------------------------------------------------------------------------------------------------
# # Specify the path to the feature class
# fc_path = r'D:\1_BVIEER\3rd_sem\Programming for GIS- III Mr. Ronit Jadhav\Assignments\Assignment_2\Data\ProProject_Practical_Two\World_data.gdb\Lakes'
#
# # Describe the feature class
# desc = arcpy.Describe(fc_path)
#
# # Access and print specific properties
# print(f"Shape Type: {desc.shapeType}")

# -----------------------------------------------------------------------------------------------------------------------
# Field names and its respective type.
# -----------------------------------------------------------------------------------------------------------------------

# # Specify the path to the feature class
# fc_path = r'D:\1_BVIEER\3rd_sem\Programming for GIS- III Mr. Ronit Jadhav\Assignments\Assignment_2\Data\ProProject_Practical_Two\World_data.gdb\Lakes'
#
# # Describe the feature class
# desc = arcpy.Describe(fc_path)
#
# # Access and print specific properties
# print(f"Feature Class Name: {desc.name}")
# print(f"Data Type: {desc.dataType}")

# *****************************************************************************************************************************
# Task 3: Describe the “erelev” raster from the RASTER_DATA folder and print the following:
# Band count
# -----------------------------------------------------------------------------------------------------------------------------
# # Specify the path to the raster dataset
# raster_path = r'D:\1_BVIEER\3rd_sem\Programming For GIS II\Practical_1\Ladsat_data_from_GEE\Purbasthali_LS7_data.tif'
#
# # Describe the raster dataset
# desc = arcpy.Describe(raster_path)
#
# # Print the requested information
# print(f"Band Count: {desc.bandCount}")

# --------------------------------------------------------------------------------------------------------------------------
# Format
# --------------------------------------------------------------------------------------------------------------------------

# # Specify the path to the raster dataset
# raster_path = r'D:\1_BVIEER\3rd_sem\Programming For GIS II\Practical_1\Ladsat_data_from_GEE\Purbasthali_LS7_data.tif'
#
# # Describe the raster dataset
# desc = arcpy.Describe(raster_path)
#
# # Print the requested information
# print(f"Format: {desc.format}")

# -----------------------------------------------------------------------------------------------------------------------
# Image Base Name
# -----------------------------------------------------------------------------------------------------------------------
# # Specify the path to the raster dataset
# raster_path = r"D:\1_BVIEER\3rd_sem\Programming For GIS II\Practical_1\Ladsat_data_from_GEE\Purbasthali_LS7_data.tif"
#
# # Describe the raster dataset
# desc = arcpy.Describe(raster_path)
#
# # Print the requested information
# print(f"Base Name: {desc.basename}")

# ------------------------------------------------------------------------------------------------------------------------
# Image height and width
# ------------------------------------------------------------------------------------------------------------------------
# Create a Describe object from the raster band
desc = arcpy.Describe(r"D:\1_BVIEER\3rd_sem\Programming For GIS II\Practical_2\Output\KALNA_2011_NDVI.tif")

# Print some raster band properties

print("Height: %d" % desc.height)
print("Width:  %d" % desc.width)






Assignment 3: - 

import arcpy
import os

# # Set the workspace (replace with your workspace path)
# arcpy.env.workspace= 'D:/1_BVIEER/3rd_sem/Programming for GIS- III Mr. Ronit Jadhav/Assignments/Assignment_3/ProProject_AutomatingUsingLists/ProProject_AutomatingUsingLists.gdb'
#
# # Get a list of feature classes in the workspace
# feature_classes = arcpy.ListFeatureClasses()
#
# # Iterate through the list and print the names
# for feature_class in feature_classes:
#     print(feature_class)


# --------------------------------------------------------------------------------------------------------------------------------------------------
# Task 1: Open an already existing text file and print every line.
# --------------------------------------------------------------------------------------------------------------------------------------------------
# # Specify the path to the text file
# file_path = 'D:/1_BVIEER/3rd_sem/Programming for GIS- III Mr. Ronit Jadhav/Assignments/Assignment_3/tobu.txt'
#
# # Open the file in read mode with 'utf-8' encoding
# try:
#     with open(file_path, 'r', encoding='utf-8') as file:
#         for line in file:
#             print(line, end="")
# except FileNotFoundError:
#     print(f"The file '{file_path}' does not exist")
# except Exception as e:
#     print(f"An error occurred: {e}")


# --------------------------------------------------------------------------------------------------------------------------------------------------
# Task 2: Document field properties for the “MajorAttractions” feature class into a text file by following the below workflow:
# --------------------------------------------------------------------------------------------------------------------------------------------------
# # Step 1: Import required modules and set workspace
# arcpy.env.workspace = r"D:\1_BVIEER\3rd_sem\Programming for GIS- III Mr. Ronit Jadhav\Assignments\Assignment_3\ProProject_AutomatingUsingLists\ProProject_AutomatingUsingLists.gdb"
#
# # Step 2: Create a list of fields from the feature class
# feature_class_name = "MajorAttractions"
# fields = arcpy.ListFields(feature_class_name)
#
# # Step 3: Open a new text file and add header lines
# output_folder = r"D:\1_BVIEER\3rd_sem\Programming for GIS- III Mr. Ronit Jadhav\Assignments\Assignment_3"
# output_file_name = "MajorAttractions_FieldInfo.txt"
# output_file_path = os.path.join(output_folder, output_file_name)
#
# with open(output_file_path, 'w') as file_obj:
#     file_obj.write(f"Field properties for the '{feature_class_name}' feature class:\n\n")
#
#     # Step 4: Loop through the list of fields
#     for field in fields:
#         # Step 5: Write each field's properties to the text file
#         file_obj.write(f"Field Name: {field.name}\n")
#         file_obj.write(f"Data Type: {field.type}\n")
#         file_obj.write(f"Length: {field.length}\n")
#         file_obj.write(f"Scale: {field.scale}\n")
#         file_obj.write("\n")
# # Step 6: Indicate that the script is completed
# print(f"Field properties have been written to {output_file_path}")


# --------------------------------------------------------------------------------------------------------------------------------------------------
'''
  Write a script that buffers feature classes, with the buffer distance determined by the type of geometry. For point feature, the buffer distance 
  will be set to one value; for polyline features, the buffer distance will be set to a second value; for polygon features, the buffer distance 
  will be set to a third value.
'''
# --------------------------------------------------------------------------------------------------------------------------------------------------
# Set the workspace
arcpy.env.workspace = r"D:\1_BVIEER\3rd_sem\Programming for GIS- III Mr. Ronit Jadhav\Assignments\Assignment_3\ProProject_AutomatingUsingLists\ProProject_AutomatingUsingLists.gdb"
# List all feature classes in the workspace
fc_list = arcpy.ListFeatureClasses()
# Loop through each feature class
for fc in fc_list:
    # Describe the feature class to get its shape type
    desc_obj = arcpy.Describe(fc)
    shape_type = desc_obj.shapeType

    # Set buffer distances based on shape type
    if shape_type == "Point":
        buffer_distance = 450  # 450 feet
    elif shape_type == "Polyline":
        buffer_distance = 1500  # 1500 feet
    elif shape_type == "Polygon":
        buffer_distance = 500  # 500 feet
    # Create an output buffer feature class
    output_buffer = fc + "_Buffer"
    # Perform the buffer analysis using the specified buffer distance
    arcpy.analysis.Buffer(fc, output_buffer, f"{buffer_distance} feet")
    print(f"Buffer created for {fc} with a {buffer_distance} buffer distance.")
    print("Process Completed")


Assignment 4: - 



import arcpy
import os


# Question 1 ***********************************************************************************************************
# arcpy.management.SelectLayerByAttribute("Population", "NEW_SELECTION", "AGE = 1")
# arcpy.management.SelectLayerByLocation("State", "WITHIN_A_DISTANCE", "restaurant_lyr", "1000 feet")

# Question 2 ***********************************************************************************************************
# output_restr_within_dist = "Wilson_within_histdist_restaurant"
# output_restr_within_dist_path = os.path.join(gdb_path, output_restr_within_dist)
# arcpy.management.CopyFeatures("restaurant_lyr", output_restr_within_dist_path)

# Task 1 ***************************************************************************************************************
gdb_path = r"D:\1_BVIEER\3rd_sem\Programming for GIS- III Mr. Ronit Jadhav\Practical_4\Given_data\ProProject_Selections\ProProject_Selections.gdb"
restaurant_fc_name = "Wilson_Restaurants"

restaurant_fc_path = os.path.join(gdb_path, restaurant_fc_name)

# Feature class to feature layer
arcpy.management.MakeFeatureLayer(restaurant_fc_path,"restaurant_Layer")

# Count of all the features before selection
pre_count = arcpy.GetCount_management("restaurant_Layer")

print("Total number of restaurants = {} ".format(pre_count))

# Task 2 ***************************************************************************************************************
gdb_path = r"D:\1_BVIEER\3rd_sem\Programming for GIS- III Mr. Ronit Jadhav\Practical_4\Given_data\ProProject_Selections\ProProject_Selections.gdb"
restaurant_fc_name = "Wilson_Restaurants"
crime_fc_name = "Wilson_Crimes96"

restaurant_fc_path = os.path.join(gdb_path,restaurant_fc_name)
crime_fc_path = os.path.join(gdb_path,crime_fc_name)

arcpy.management.MakeFeatureLayer(restaurant_fc_path,"restaurant_lyr")
arcpy.management.MakeFeatureLayer(crime_fc_path,"crime_lyr")

# getting count of all the features before selection
pre_count1=arcpy.GetCount_management("restaurant_lyr")
pre_count3=arcpy.GetCount_management("crime_lyr")

# Query
arcpy.management.SelectLayerByLocation("crime_lyr","WITHIN_A_DISTANCE","restaurant_lyr","500 meters")
post_count3 =arcpy.GetCount_management("crime_lyr")
print('crime near 500 meters of restaurant = {}'.format(post_count3))

print("Process Completed")

# Task 3 ***************************************************************************************************************
gdb_path = r"D:\1_BVIEER\3rd_sem\Programming for GIS- III Mr. Ronit Jadhav\Practical_4\Given_data\ProProject_Selections\ProProject_Selections.gdb"
restaurant_fc_name = "Wilson_Restaurants"
histdist_fc_name = "Wilson_Histdist"
crime_fc_name = "Wilson_Crimes96"

restaurant_fc_path = os.path.join(gdb_path,restaurant_fc_name)
histdist_fc_path = os.path.join(gdb_path,histdist_fc_name)
crime_fc_path = os.path.join(gdb_path,crime_fc_name)
 
arcpy.management.MakeFeatureLayer(restaurant_fc_path,"restaurant_lyr")
arcpy.management.MakeFeatureLayer(histdist_fc_path,"histdist_lyr")
arcpy.management.MakeFeatureLayer(crime_fc_path,"crime_lyr")

# getting count of all the features before selection
pre_count1=arcpy.GetCount_management("restaurant_lyr")
pre_count2=arcpy.GetCount_management("histdist_lyr")
pre_count3=arcpy.GetCount_management("crime_lyr")

print('Total Restaurants before selection = {}'.format(pre_count1[0]))
print('Total historic district before selection = {}'.format(pre_count2[0]))
print('Total crime before selection = {}'.format(pre_count3[0]))

arcpy.management.SelectLayerByAttribute("restaurant_lyr","NEW_SELECTION","ALCOHOL=1")
post_count1 = arcpy.GetCount_management("restaurant_lyr")
print('total restaurants serves alcohol = {}'.format(post_count1))

arcpy.management.SelectLayerByLocation("restaurant_lyr","WITHIN_A_DISTANCE","histdist_lyr","1000 feet","SUBSET_SELECTION")
post_count2 =arcpy.GetCount_management("restaurant_lyr")
print('total restaurants serves alcohol within 1000 feet of histdist = {}'.format(post_count2))

arcpy.management.SelectLayerByLocation("crime_lyr","WITHIN_A_DISTANCE","restaurant_lyr","500 feet")
post_count3 =arcpy.GetCount_management("crime_lyr")
print('crime near 500 feet of restaurant = {}'.format(post_count3))

arcpy.management.SelectLayerByAttribute("crime_lyr","SUBSET_SELECTION","ALCOHOL>0")
post_count4 = arcpy.GetCount_management("crime_lyr")
print('Alcohol related crime = {}'.format(post_count4))


print("Process Completed")


Assignment 5: -


# Task 1 ***************************************************************************************************************
import arcpy
import os
gdp_path = r"D:\1_BVIEER\3rd_sem\Programming for GIS- III Mr. Ronit Jadhav\Assignments\Assignment_5\ProProject_Cursors\ProProject_Cursors\ProProject_Cursors.gdb"
fc_name = "MajorAttractions"
fc_path = os.path.join(gdp_path,fc_name)

field_list = ["NAME","ADDR"]

with arcpy.da.SearchCursor(fc_path,field_list) as s_cursor:
    for row in s_cursor:
        print("Name:{} |  Address:{}".format(row[0], row[1]))
    del s_cursor

# Task 2 ***************************************************************************************************************
# import arcpy
# import os
gdp_path = r"D:\1_BVIEER\3rd_sem\Programming for GIS- III Mr. Ronit Jadhav\Assignments\Assignment_5\ProProject_Cursors\ProProject_Cursors\ProProject_Cursors.gdb"

fc_name = "MajorAttractions"
fc_path = os.path.join(gdp_path,fc_name)

field_list = ["NAME","ADDR","ESTAB"]

with arcpy.da.SearchCursor(fc_path,field_list,"ESTAB>1970") as s_cursor:
    for row in s_cursor:
        print("Name:{},  Establishment:{}".format(row[0], row[2]))
    del s_cursor
print("Process completed")

# Task 3 ***************************************************************************************************************
import arcpy
import os
gdp_path = r"D:\1_BVIEER\3rd_sem\Programming for GIS- III Mr. Ronit Jadhav\Assignments\Assignment_5\ProProject_Cursors\ProProject_Cursors\ProProject_Cursors.gdb"

fc_name = "MajorAttractions"
fc_path = os.path.join(gdp_path,fc_name)

field_list = ["NAME","SHAPE@X","SHAPE@Y"]
print("-------------------------- majorAttraction and its coordinates -------------------------------")
with arcpy.da.SearchCursor(fc_path,field_list) as s_cursor:
    for row in s_cursor:
        print("Name: {}, X-corrdinates:{},  Y-coordinates:{}".format(row[0],row[1], row[2]))
    del s_cursor


Assignment 6: - 


# Task 1 ***************************************************************************************************************
import arcpy
import os
gdp_path = r"D:\1_BVIEER\3rd_sem\Programming for GIS- III Mr. Ronit Jadhav\Assignments\Assignment_5\ProProject_Cursors\ProProject_Cursors\ProProject_Cursors.gdb"
fc_name = "MajorAttractions"

fc_path = os.path.join(gdp_path,fc_name)

field_list = ["NAME","ESTAB","HISTORIC"]

with arcpy.da.UpdateCursor(fc_path,field_list) as U_cursor:
    for row in U_cursor:

        if row[1]<1960:
            row[2] = "yes"
        else:
            row[2] = "No"
        U_cursor.updateRow(row)

print("Process Completed")

# Task 2 ***************************************************************************************************************
gdp_path = r"D:\1_BVIEER\3rd_sem\Programming for GIS- III Mr. Ronit Jadhav\Assignments\Assignment_5\ProProject_Cursors\ProProject_Cursors\ProProject_Cursors.gdb"
fc_name = "MajorAttractions"

fc_path = os.path.join(gdp_path,fc_name)

field_list = ["NAME","ESTAB","ADDR","CITYNM","ZIP","EMP","ACRES"]

record_1 = (" Five Star Restaurant",2021,"841 STREET","SAN DIEGO",92101,150,10)
record_2 = (" New Town Restaurant ",2022,"842 STREET","SAN DIEGO",92105,140,15)

i_cursor = arcpy.da.InsertCursor(fc_path,field_list)
i_cursor.insertRow(record_1)
i_cursor.insertRow(record_2)
print("Process Completed")
