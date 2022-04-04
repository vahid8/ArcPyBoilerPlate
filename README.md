# ArcPyBoilerPlate
### Check existance of a layer
```
arcpy.Exists(layername)
```

### Delete a layer or gdb
```
arcpy.Delete_management(layerName)
arcpy.Delete_management(gdbName)
```
### Get available features, fields ,...
```
arcpy.env.workspace = gdb_path

feature_list = arcpy.ListFeatureClasses()
table_list = arcpy.ListTables("*")
ras_list = arcpy.ListRasters()

# Get the name of columns( fields) in feature layer
fields = [f.name for f in arcpy.ListFields(feature_layer_path)]
# Get properties of a feature layer
desc = arcpy.Describe(item)
print(f" shape type: {desc.shapeType}")
print(f" feature type: {desc.featureType}")

```


### Adding new column to layer
```
arcpy.management.AddField(in_table, field_name, field_type, {field_precision}, {field_scale}, {field_length}, {field_alias}, {field_is_nullable}, {field_is_required}, {field_domain})
examples :
arcpy.AddField_management(layer_name, "SM4L", "Double", 2, 10, field_alias="SM4L[mm]")
arcpy.AddField_management(layer_name, "Bildname", "TEXT")
```

### Adding a column from one layer (table) to another layer
```
arcpy.management.JoinField(in_data, in_field, join_table, join_field, {fields})
arcpy.management.JoinField(fc_pointsAtLine, 'OBJECTID', fc_elevationPoints, 'OBJECTID',['RASTERVALU'])
```

### Copy feature layer from one layer to another ( filter can be applied)
```
CopyFeatures_management (in_features, out_feature_class, {config_keyword}, {spatial_grid_1}, {spatial_grid_2}, {spatial_grid_3})
```
### Reading and getting info about geodatabase using arcpy 
``` 
arcpy.env.workspace  =r"D:\EssenApp\output\ZEB1\ZEB_2019_2020_2\Bewertungsabschnitte_neu4_TUEV_1990.gdb"
# print(f"print(arcpy.ListFeatureCLasses(aa)){arcpy.ListFeatureCLasses(aa)}")
aa = arcpy.ListTables("*")
bb = arcpy.ListFeatureClasses()
print(f"arcpy.ListTables(){aa}")
print(f"arcpy.ListFeatureClasses(){bb}")
for feature in bb:
    print(feature)
    for f in arcpy.ListFields(feature):
        print(f.name)  
```
