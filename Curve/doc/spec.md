Entity: Curve  
=============  
[Open License](https://github.com/smart-data-models//dataModel.WaterDistributionManagementEPANET/blob/master/Curve/LICENSE.md)  
[document generated automatically](https://docs.google.com/presentation/d/e/2PACX-1vTs-Ng5dIAwkg91oTTUdt8ua7woBXhPnwavZ0FxgR8BsAI_Ek3C5q97Nd94HS8KhP-r_quD4H0fgyt3/pub?start=false&loop=false&delayms=3000#slide=id.gb715ace035_0_60)  
Global description: **This entity contains a harmonised description of a generic curve made for the Water Network Management domain. This entity is primarily associated with the water management vertical and related IoT applications.**  

## List of properties  

- `address`: The mailing address  - `alternateName`: An alternative name for this item  - `areaServed`: The geographic area where a service or offered item is provided  - `curveType`: Entity's curve type. Enum:'FLOW-HEAD, FLOW-EFFICIENCY, FLOW-HEADLOSS, LEVEL-VOLUME'  - `dataProvider`: A sequence of characters identifying the provider of the harmonised data entity.  - `dateCreated`: Entity creation timestamp. This will usually be allocated by the storage platform.  - `dateModified`: Timestamp of the last modification of the entity. This will usually be allocated by the storage platform.  - `description`: A description of this item  - `id`: Unique identifier of the entity  - `location`: Geojson reference to the item. It can be Point, LineString, Polygon, MultiPoint, MultiLineString or MultiPolygon  - `name`: The name of this item.  - `owner`: A List containing a JSON encoded sequence of characters referencing the unique Ids of the owner(s)  - `seeAlso`: list of uri pointing to additional resources about the item  - `source`: A sequence of characters giving the original source of the entity data as a URL. Recommended to be the fully qualified domain name of the source provider, or the URL to the source object.  - `tag`: An optional text string used to assign the pipe to a category, perhaps one based on age or material  - `type`: NGSI-LD Entity Type. It must be equal to Curve.  - `xData`: X data points for the curve  - `yData`: Y data points for the curve    
Required properties  
- `curveType`  - `id`  - `type`  - `xData`  - `yData`  ## Data Model description of properties  
Sorted alphabetically (click for details)  
<details><summary><strong>full yaml details</strong></summary>    
```yaml  
Curve:    
  description: 'This entity contains a harmonised description of a generic curve made for the Water Network Management domain. This entity is primarily associated with the water management vertical and related IoT applications.'    
  properties:    
    address:    
      description: 'The mailing address'    
      properties:    
        addressCountry:    
          description: 'Property. The country. For example, Spain. Model:''https://schema.org/addressCountry'''    
          type: string    
        addressLocality:    
          description: 'Property. The locality in which the street address is, and which is in the region. Model:''https://schema.org/addressLocality'''    
          type: string    
        addressRegion:    
          description: 'Property. The region in which the locality is, and which is in the country. Model:''https://schema.org/addressRegion'''    
          type: string    
        postOfficeBoxNumber:    
          description: 'Property. The post office box number for PO box addresses. For example, 03578. Model:''https://schema.org/postOfficeBoxNumber'''    
          type: string    
        postalCode:    
          description: 'Property. The postal code. For example, 24004. Model:''https://schema.org/https://schema.org/postalCode'''    
          type: string    
        streetAddress:    
          description: 'Property. The street address. Model:''https://schema.org/streetAddress'''    
          type: string    
      type: Property    
      x-ngsi:    
        model: https://schema.org/address    
    alternateName:    
      description: 'An alternative name for this item'    
      type: Property    
    areaServed:    
      description: 'The geographic area where a service or offered item is provided'    
      type: Property    
      x-ngsi:    
        model: https://schema.org/Text    
    curveType:    
      description: 'Entity''s curve type. Enum:''FLOW-HEAD, FLOW-EFFICIENCY, FLOW-HEADLOSS, LEVEL-VOLUME'''    
      enum:    
        - FLOW-HEAD    
        - FLOW-EFFICIENCY    
        - FLOW-HEADLOSS    
        - LEVEL-VOLUME    
      type: Property    
    dataProvider:    
      description: 'A sequence of characters identifying the provider of the harmonised data entity.'    
      type: Property    
    dateCreated:    
      description: 'Entity creation timestamp. This will usually be allocated by the storage platform.'    
      format: date-time    
      type: Property    
    dateModified:    
      description: 'Timestamp of the last modification of the entity. This will usually be allocated by the storage platform.'    
      format: date-time    
      type: Property    
    description:    
      description: 'A description of this item'    
      type: Property    
    id:    
      anyOf: &curve_-_properties_-_owner_-_items_-_anyof    
        - description: 'Property. Identifier format of any NGSI entity'    
          maxLength: 256    
          minLength: 1    
          pattern: ^[\w\-\.\{\}\$\+\*\[\]`|~^@!,:\\]+$    
          type: string    
        - description: 'Property. Identifier format of any NGSI entity'    
          format: uri    
          type: string    
      description: 'Unique identifier of the entity'    
      type: Property    
    location:    
      description: 'Geojson reference to the item. It can be Point, LineString, Polygon, MultiPoint, MultiLineString or MultiPolygon'    
      oneOf:    
        - description: 'Geoproperty. Geojson reference to the item. Point'    
          properties:    
            bbox:    
              items:    
                type: number    
              minItems: 4    
              type: array    
            coordinates:    
              items:    
                type: number    
              minItems: 2    
              type: array    
            type:    
              enum:    
                - Point    
              type: string    
          required:    
            - type    
            - coordinates    
          title: 'GeoJSON Point'    
          type: object    
        - description: 'Geoproperty. Geojson reference to the item. LineString'    
          properties:    
            bbox:    
              items:    
                type: number    
              minItems: 4    
              type: array    
            coordinates:    
              items:    
                items:    
                  type: number    
                minItems: 2    
                type: array    
              minItems: 2    
              type: array    
            type:    
              enum:    
                - LineString    
              type: string    
          required:    
            - type    
            - coordinates    
          title: 'GeoJSON LineString'    
          type: object    
        - description: 'Geoproperty. Geojson reference to the item. Polygon'    
          properties:    
            bbox:    
              items:    
                type: number    
              minItems: 4    
              type: array    
            coordinates:    
              items:    
                items:    
                  items:    
                    type: number    
                  minItems: 2    
                  type: array    
                minItems: 4    
                type: array    
              type: array    
            type:    
              enum:    
                - Polygon    
              type: string    
          required:    
            - type    
            - coordinates    
          title: 'GeoJSON Polygon'    
          type: object    
        - description: 'Geoproperty. Geojson reference to the item. MultiPoint'    
          properties:    
            bbox:    
              items:    
                type: number    
              minItems: 4    
              type: array    
            coordinates:    
              items:    
                items:    
                  type: number    
                minItems: 2    
                type: array    
              type: array    
            type:    
              enum:    
                - MultiPoint    
              type: string    
          required:    
            - type    
            - coordinates    
          title: 'GeoJSON MultiPoint'    
          type: object    
        - description: 'Geoproperty. Geojson reference to the item. MultiLineString'    
          properties:    
            bbox:    
              items:    
                type: number    
              minItems: 4    
              type: array    
            coordinates:    
              items:    
                items:    
                  items:    
                    type: number    
                  minItems: 2    
                  type: array    
                minItems: 2    
                type: array    
              type: array    
            type:    
              enum:    
                - MultiLineString    
              type: string    
          required:    
            - type    
            - coordinates    
          title: 'GeoJSON MultiLineString'    
          type: object    
        - description: 'Geoproperty. Geojson reference to the item. MultiLineString'    
          properties:    
            bbox:    
              items:    
                type: number    
              minItems: 4    
              type: array    
            coordinates:    
              items:    
                items:    
                  items:    
                    items:    
                      type: number    
                    minItems: 2    
                    type: array    
                  minItems: 4    
                  type: array    
                type: array    
              type: array    
            type:    
              enum:    
                - MultiPolygon    
              type: string    
          required:    
            - type    
            - coordinates    
          title: 'GeoJSON MultiPolygon'    
          type: object    
      type: Geoproperty    
    name:    
      description: 'The name of this item.'    
      type: Property    
    owner:    
      description: 'A List containing a JSON encoded sequence of characters referencing the unique Ids of the owner(s)'    
      items:    
        anyOf: *curve_-_properties_-_owner_-_items_-_anyof    
        description: 'Property. Unique identifier of the entity'    
      type: Property    
    seeAlso:    
      description: 'list of uri pointing to additional resources about the item'    
      oneOf:    
        - items:    
            format: uri    
            type: string    
          minItems: 1    
          type: array    
        - format: uri    
          type: string    
      type: Property    
    source:    
      description: 'A sequence of characters giving the original source of the entity data as a URL. Recommended to be the fully qualified domain name of the source provider, or the URL to the source object.'    
      type: Property    
    tag:    
      description: 'An optional text string used to assign the pipe to a category, perhaps one based on age or material'    
      type: Property    
      x-ngsi:    
        model: https://schema.org/Text    
    type:    
      description: 'NGSI-LD Entity Type. It must be equal to Curve.'    
      enum:    
        - Curve    
      type: Property    
    xData:    
      description: 'X data points for the curve'    
      items:    
        type: number    
      type: Property    
    yData:    
      description: 'Y data points for the curve'    
      items:    
        type: number    
      type: Property    
  required:    
    - id    
    - type    
    - curveType    
    - xData    
    - yData    
  type: object    
```  
</details>    
## Example payloads    
#### Curve NGSI-v2 key-values Example    
Here is an example of a Curve in JSON-LD format as key-values. This is compatible with NGSI-v2 when  using `options=keyValues` and returns the context data of an individual entity.  
```json  
{  
  "id": "fAM-8ca3-4533-a2eb-12015",  
  "type": "Curve",  
  "curveType": "FLOW-HEAD",  
  "xData": [  
    0.5692,  
    0.4647  
  ],  
  "yData": [  
    0.5692,  
    0.4647  
  ],  
  "description": "Free Text",  
  "tag": "DMA1"  
}  
```  
#### Curve NGSI-v2 normalized Example    
Here is an example of a Curve in JSON-LD format as normalized. This is compatible with NGSI-v2 when not using options and returns the context data of an individual entity.  
```json  
{  
    "id": "fAM-8ca3-4533-a2eb-12015",  
    "type": "Curve",  
    "dateCreated": {  
        "type": "DateTime",  
        "value": "2020-02-16T17:43:00Z"  
    },  
    "dateModified": {  
        "type": "DateTime",  
        "value": "2020-02-16T17:43:00Z"  
    },  
    "curveType": {  
        "value": "FLOW-HEAD"  
    },  
    "xData": {  
        "value": [  
            0.5692,  
            0.4647  
        ]  
    },  
    "yData": {  
        "value": [  
            0.5692,  
            0.4647  
        ]  
    },  
    "description": {  
        "value": "Free Text"  
    },  
    "tag": {  
        "value": "DMA1"  
    }  
}  
```  
#### Curve NGSI-LD key-values Example    
Here is an example of a Curve in JSON-LD format as key-values. This is compatible with NGSI-LD when  using `options=keyValues` and returns the context data of an individual entity.  
```json  
{  
  "@context": [  
    "https://smartdatamodels.org/context.jsonld"  
  ],  
  "id": "fAM-8ca3-4533-a2eb-12015",  
  "type": "Curve",  
  "curveType": "FLOW-HEAD",  
  "xData": [  
    0.5692,  
    0.4647  
  ],  
  "yData": [  
    0.5692,  
    0.4647  
  ],  
  "description": "Free Text",  
  "tag": "DMA1"  
}  
```  
#### Curve NGSI-LD normalized Example    
Here is an example of a Curve in JSON-LD format as normalized. This is compatible with NGSI-LD when not using options and returns the context data of an individual entity.  
```json  
{  
  "id": "urn:ngsi-ld:Curve:fAM-8ca3-4533-a2eb-12015",  
  "type": "Curve",  
  "createdAt": "2020-02-16T17:43:00Z",  
  "modifiedAt": "2020-02-16T17:43:00Z",  
  "curveType": {  
    "type": "Property",  
    "value": "FLOW-HEAD"  
  },  
  "xData": {  
    "type": "Property",  
    "value": [  
      0.5692,  
      0.4647  
    ],  
    "unitCode": "C62"  
  },  
  "yData": {  
    "type": "Property",  
    "value": [  
      0.5692,  
      0.4647  
    ],  
    "unitCode": "C62"  
  },  
  "description": {  
    "type": "Property",  
    "value": "Free Text"  
  },  
  "tag": {  
    "type": "Property",  
    "value": "DMA1"  
  },  
  "@context": [  
    "https://smartdatamodels.org/context.jsonld"  
  ]  
}  
```  
