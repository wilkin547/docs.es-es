---
title: "Generar las relaciones de DataSet desde la definici&#243;n de esquemas XML (XSD) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1c9a1413-c0d2-4447-88ba-9a2b0cbc0aa8
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Generar las relaciones de DataSet desde la definici&#243;n de esquemas XML (XSD)
En un <xref:System.Data.DataSet>, para formar una asociación entre dos o más columnas se debe crear una relación primaria\-secundaria.  Hay tres formas de representar una relación de **DataSet** dentro de un esquema de lenguaje de definición de esquemas XML \(XSD\):  
  
-   Especificar tipos complejos anidados.  
  
-   Utilizar la anotación **msdata:Relationship**.  
  
-   Especificar **xs:keyref** sin la anotación **msdata:ConstraintOnly**.  
  
## Tipos complejos anidados  
 Las definiciones de tipos complejos anidados de un esquema indican las relaciones primaria\-secundaria de los elementos.  El siguiente fragmento de esquema XML muestra que **OrderDetail** es un elemento secundario del elemento **Order**.  
  
```  
<xs:element name="Order">  
  <xs:complexType>  
     <xs:sequence>          
       <xs:element name="OrderDetail" />  
           <xs:complexType>               
           </xs:complexType>  
     </xs:sequence>  
  </xs:complexType>  
</xs:element>  
```  
  
 El proceso de asignación del esquema XML crea en el **DataSet** tablas que se corresponden con los tipos complejos anidados del esquema.  También crea columnas adicionales que se utilizan como columnas primaria**\-**secundaria para las tablas generadas.  Tenga en cuenta que estas columnas primaria**\-**secundaria especifican relaciones, lo cual no es lo mismo que especificar restricciones de clave principal y clave externa.  
  
## Anotación msdata:Relationship  
 La anotación **msdata:Relationship** le permite especificar explícitamente relaciones primaria\-secundaria entre los elementos del esquema que no están anidados.  En el siguiente ejemplo se muestra la estructura del elemento **Relationship**.  
  
```  
  
  <msdata:Relationship name="CustOrderRelationship"    
msdata:parent=""    
msdata:child=""    
msdata:parentkey=""    
msdata:childkey="" />  
```  
  
 Los atributos de la anotación **msdata:Relationship** identifican los elementos que forman parte de la relación primaria\-secundaria, así como los elementos y atributos **parentkey** y **childkey** que participan en la relación.  El proceso de asignación utiliza esta información para generar tablas en el **DataSet** y para crear la relación de clave principal y clave externa entre estas tablas.  
  
 Por ejemplo, en el siguiente fragmento de esquema se especifica que los elementos **Order** y **OrderDetail** son del mismo nivel \(no están anidados\).  El esquema especifica una anotación **msdata:Relationship**, que especifica la relación primaria\-secundaria entre estos dos elementos.  En este caso, es preciso especificar una relación explícita mediante la anotación **msdata:Relationship**.  
  
```  
 <xs:element name="MyDataSet" msdata:IsDataSet="true">  
  <xs:complexType>  
    <xs:choice maxOccurs="unbounded">  
        <xs:element name="OrderDetail">  
          <xs:complexType>  
  
          </xs:complexType>  
       </xs:element>  
       <xs:element name="Order">  
          <xs:complexType>  
  
          </xs:complexType>  
       </xs:element>  
    </xs:choice>  
  </xs:complexType>  
</xs:element>  
   <xs:annotation>  
     <xs:appinfo>  
       <msdata:Relationship name="OrdOrdDetailRelation"  
          msdata:parent="Order"  
          msdata:child="OrderDetail"   
          msdata:parentkey="OrderNumber"  
          msdata:childkey="OrderNo"/>  
     </xs:appinfo>  
  </xs:annotation>  
  
```  
  
 El proceso de asignación utiliza el elemento **Relationship** para crear una relación primaria\-secundaria entre la columna **OrderNumber** de la tabla **Order** y la columna **OrderNo** de la tabla **OrderDetail** del **DataSet**.  El proceso de asignación sólo especifica la relación; no especifica automáticamente ninguna restricción para los valores de estas columnas, como ocurre en las restricciones de clave principal y clave externa de las bases de datos relacionales.  
  
### En esta sección  
 [Asignar relaciones implícitas entre elementos de esquema anidados](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-implicit-relations-between-nested-schema-elements.md)  
 Describe las restricciones y las relaciones que se crean de forma implícita en un **DataSet** cuando se encuentran elementos anidados en el esquema XML.  
  
 [Asignar relaciones especificadas para elementos anidados](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-relations-specified-for-nested-elements.md)  
 Describe cómo establecer explícitamente relaciones en un **DataSet** para los elementos anidados del esquema XML.  
  
 [Especificar relaciones entre elementos sin anidamiento](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/specify-relations-between-elements-with-no-nesting.md)  
 Describe cómo crear relaciones en un **DataSet** entre elementos del esquema XML que no están anidados.  
  
### Secciones relacionadas  
 [Derivar la estructura relacional de DataSet desde la definición de esquema XML \(XSD\)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 Describe la estructura relacional, o esquema, de un **DataSet** que se crea a partir del esquema del lenguaje de definición de esquemas XML \(XSD\).  
  
 [Asignar restricciones de esquema XML \(XSD\) a las restricciones de DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 Describe los elementos de esquema XML utilizados para crear restricciones de clave única y externa en un **DataSet**.  
  
## Vea también  
 [Proveedores administrados de ADO.NET y centro de desarrolladores de conjuntos de datos](http://go.microsoft.com/fwlink/?LinkId=217917)