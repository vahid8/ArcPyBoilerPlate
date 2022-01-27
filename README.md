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
