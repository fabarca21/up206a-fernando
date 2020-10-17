```python
import geopandas as gpd
```


```python
usd = gpd.read_file('http://s3-us-west-2.amazonaws.com/boundaries.latimes.com/archive/1.0/boundary-set/unified-school-districts-2012.geojson')
```


```python
type(usd)
```




    geopandas.geodataframe.GeoDataFrame




```python
usd.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>kind</th>
      <th>external_id</th>
      <th>name</th>
      <th>slug</th>
      <th>set</th>
      <th>metadata</th>
      <th>resource_uri</th>
      <th>geometry</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Unified School District (2012)</td>
      <td>0601620</td>
      <td>ABC Unified School District</td>
      <td>abc-unified-school-district-unified-school-dis...</td>
      <td>/1.0/boundary-set/unified-school-districts-2012/</td>
      <td>{'INTPTLAT': '+33.8637711', 'SDTYP': '', 'NAME...</td>
      <td>/1.0/boundary/abc-unified-school-district-unif...</td>
      <td>MULTIPOLYGON (((-118.10021 33.84807, -118.1030...</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Unified School District (2012)</td>
      <td>0600001</td>
      <td>Acton-Agua Dulce Unified School District</td>
      <td>acton-agua-dulce-unified-school-district-unifi...</td>
      <td>/1.0/boundary-set/unified-school-districts-2012/</td>
      <td>{'INTPTLAT': '+34.4485137', 'SDTYP': '', 'NAME...</td>
      <td>/1.0/boundary/acton-agua-dulce-unified-school-...</td>
      <td>MULTIPOLYGON (((-118.37894 34.46763, -118.3775...</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Unified School District (2012)</td>
      <td>0601770</td>
      <td>Alameda City Unified School District</td>
      <td>alameda-city-unified-school-district-unified-s...</td>
      <td>/1.0/boundary-set/unified-school-districts-2012/</td>
      <td>{'INTPTLAT': '+37.7644706', 'SDTYP': '', 'NAME...</td>
      <td>/1.0/boundary/alameda-city-unified-school-dist...</td>
      <td>MULTIPOLYGON (((-122.34028 37.80063, -122.3146...</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Unified School District (2012)</td>
      <td>0601860</td>
      <td>Albany City Unified School District</td>
      <td>albany-city-unified-school-district-unified-sc...</td>
      <td>/1.0/boundary-set/unified-school-districts-2012/</td>
      <td>{'INTPTLAT': '+37.8886213', 'SDTYP': '', 'NAME...</td>
      <td>/1.0/boundary/albany-city-unified-school-distr...</td>
      <td>MULTIPOLYGON (((-122.36898 37.87013, -122.3737...</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Unified School District (2012)</td>
      <td>0600153</td>
      <td>Alhambra Unified School District</td>
      <td>alhambra-unified-school-district-unified-schoo...</td>
      <td>/1.0/boundary-set/unified-school-districts-2012/</td>
      <td>{'INTPTLAT': '+34.0746675', 'SDTYP': '', 'NAME...</td>
      <td>/1.0/boundary/alhambra-unified-school-district...</td>
      <td>MULTIPOLYGON (((-118.16928 34.05035, -118.1692...</td>
    </tr>
  </tbody>
</table>
</div>




```python
usd.shape
```




    (337, 8)




```python
usd.info
```




    <bound method DataFrame.info of                                kind external_id  \
    0    Unified School District (2012)     0601620   
    1    Unified School District (2012)     0600001   
    2    Unified School District (2012)     0601770   
    3    Unified School District (2012)     0601860   
    4    Unified School District (2012)     0600153   
    ..                              ...         ...   
    332  Unified School District (2012)     0642930   
    333  Unified School District (2012)     0643080   
    334  Unified School District (2012)     0600160   
    335  Unified School District (2012)     0643470   
    336  Unified School District (2012)     0643560   
    
                                                   name  \
    0                       ABC Unified School District   
    1          Acton-Agua Dulce Unified School District   
    2              Alameda City Unified School District   
    3               Albany City Unified School District   
    4                  Alhambra Unified School District   
    ..                                              ...   
    332           Winters Joint Unified School District   
    333          Woodland Joint Unified School District   
    334                Yosemite Unified School District   
    335               Yuba City Unified School District   
    336  Yucaipa-Calimesa Joint Unified School District   
    
                                                      slug  \
    0    abc-unified-school-district-unified-school-dis...   
    1    acton-agua-dulce-unified-school-district-unifi...   
    2    alameda-city-unified-school-district-unified-s...   
    3    albany-city-unified-school-district-unified-sc...   
    4    alhambra-unified-school-district-unified-schoo...   
    ..                                                 ...   
    332  winters-joint-unified-school-district-unified-...   
    333  woodland-joint-unified-school-district-unified...   
    334  yosemite-unified-school-district-unified-schoo...   
    335  yuba-city-unified-school-district-unified-scho...   
    336  yucaipa-calimesa-joint-unified-school-district...   
    
                                                      set  \
    0    /1.0/boundary-set/unified-school-districts-2012/   
    1    /1.0/boundary-set/unified-school-districts-2012/   
    2    /1.0/boundary-set/unified-school-districts-2012/   
    3    /1.0/boundary-set/unified-school-districts-2012/   
    4    /1.0/boundary-set/unified-school-districts-2012/   
    ..                                                ...   
    332  /1.0/boundary-set/unified-school-districts-2012/   
    333  /1.0/boundary-set/unified-school-districts-2012/   
    334  /1.0/boundary-set/unified-school-districts-2012/   
    335  /1.0/boundary-set/unified-school-districts-2012/   
    336  /1.0/boundary-set/unified-school-districts-2012/   
    
                                                  metadata  \
    0    {'INTPTLAT': '+33.8637711', 'SDTYP': '', 'NAME...   
    1    {'INTPTLAT': '+34.4485137', 'SDTYP': '', 'NAME...   
    2    {'INTPTLAT': '+37.7644706', 'SDTYP': '', 'NAME...   
    3    {'INTPTLAT': '+37.8886213', 'SDTYP': '', 'NAME...   
    4    {'INTPTLAT': '+34.0746675', 'SDTYP': '', 'NAME...   
    ..                                                 ...   
    332  {'INTPTLAT': '+38.5684863', 'SDTYP': '', 'NAME...   
    333  {'INTPTLAT': '+38.7202217', 'SDTYP': '', 'NAME...   
    334  {'INTPTLAT': '+37.2309353', 'SDTYP': '', 'NAME...   
    335  {'INTPTLAT': '+39.0342246', 'SDTYP': '', 'NAME...   
    336  {'INTPTLAT': '+34.0512508', 'SDTYP': '', 'NAME...   
    
                                              resource_uri  \
    0    /1.0/boundary/abc-unified-school-district-unif...   
    1    /1.0/boundary/acton-agua-dulce-unified-school-...   
    2    /1.0/boundary/alameda-city-unified-school-dist...   
    3    /1.0/boundary/albany-city-unified-school-distr...   
    4    /1.0/boundary/alhambra-unified-school-district...   
    ..                                                 ...   
    332  /1.0/boundary/winters-joint-unified-school-dis...   
    333  /1.0/boundary/woodland-joint-unified-school-di...   
    334  /1.0/boundary/yosemite-unified-school-district...   
    335  /1.0/boundary/yuba-city-unified-school-distric...   
    336  /1.0/boundary/yucaipa-calimesa-joint-unified-s...   
    
                                                  geometry  
    0    MULTIPOLYGON (((-118.10021 33.84807, -118.1030...  
    1    MULTIPOLYGON (((-118.37894 34.46763, -118.3775...  
    2    MULTIPOLYGON (((-122.34028 37.80063, -122.3146...  
    3    MULTIPOLYGON (((-122.36898 37.87013, -122.3737...  
    4    MULTIPOLYGON (((-118.16928 34.05035, -118.1692...  
    ..                                                 ...  
    332  MULTIPOLYGON (((-122.11126 38.47711, -122.1081...  
    333  MULTIPOLYGON (((-121.93429 38.60010, -121.9345...  
    334  MULTIPOLYGON (((-119.87331 37.24000, -119.8734...  
    335  MULTIPOLYGON (((-121.73399 38.99960, -121.7361...  
    336  MULTIPOLYGON (((-117.13881 34.03330, -117.1387...  
    
    [337 rows x 8 columns]>




```python

```
