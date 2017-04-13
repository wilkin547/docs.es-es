---
title: "Asignar relaciones especificadas para elementos anidados | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 24a2d3e5-4af7-4f9a-ab7a-fe6684c9e4fe
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Asignar relaciones especificadas para elementos anidados
Un esquema puede incluir una anotación **msdata:Relationship** para especificar explícitamente la asignación entre dos elementos cualesquiera del esquema.  Los dos elementos especificados en **msdata:Relationship** pueden estar anidados en el esquema, si bien no es necesario.  El proceso de asignación utiliza **msdata:Relationship** en el esquema para generar la relación de clave principal y clave externa entre las dos columnas.  
  
 En el siguiente ejemplo se muestra un esquema XML donde el elemento **OrderDetail** es un elemento secundario de **Order**.  La anotación **msdata:Relationship** identifica esta relación primaria\-secundaria y especifica que la columna **OrderNumber** de la tabla **Order** resultante está relacionada con la columna **OrderNo** de la tabla **OrderDetail** resultante.  
  
```  
<xs:schema id="MyDataSet" xmlns=""   
            xmlns:xs="http://www.w3.org/2001/XMLSchema"   
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
<xs:element name="MyDataSet" msdata:IsDataSet="true">  
 <xs:complexType>  
  <xs:choice maxOccurs="unbounded">  
   <xs:element name="Order">  
    <xs:complexType>  
     <xs:sequence>  
       <xs:element name="OrderNumber" type="xs:string" />  
       <xs:element name="EmpNumber" type="xs:string" />  
       <xs:element name="OrderDetail">  
          <xs:annotation>  
           <xs:appinfo>  
            <msdata:Relationship name="OrdODRelation"   
                                msdata:parent="Order"   
                                msdata:child="OrderDetail"   
                                msdata:parentkey="OrderNumber"   
                                msdata:childkey="OrderNo"/>  
           </xs:appinfo>  
          </xs:annotation>  
          <xs:complexType>  
            <xs:sequence>  
             <xs:element name="OrderNo" type="xs:string" />  
             <xs:element name="ItemNo" type="xs:string" />  
            </xs:sequence>  
         </xs:complexType>  
       </xs:element>  
     </xs:sequence>  
    </xs:complexType>  
   </xs:element>  
  </xs:choice>  
 </xs:complexType>  
</xs:element>  
</xs:schema>  
```  
  
 El proceso de asignación del esquema XML crea lo siguiente en el <xref:System.Data.DataSet>:  
  
-   Una tabla **Order** y una tabla **OrderDetail**.  
  
    ```  
    Order(OrderNumber, EmpNumber)  
    OrderDetail(OrderNo, ItemNo)  
    ```  
  
-   Una relación entre las tablas **Order** y **OrderDetail**.  La propiedad **Nested** de esta relación tiene el valor **True**, ya que los elementos **Order** y **OrderDetail** están anidados en el esquema.  
  
    ```  
    ParentTable: Order  
    ParentColumns: OrderNumber   
    ChildTable: OrderDetail  
    ChildColumns: OrderNo   
    RelationName: OrdODRelation  
    Nested: True  
    ```  
  
 El proceso de asignación no crea ninguna restricción.  
  
## Vea también  
 [Generar las relaciones de DataSet desde la definición de esquemas XML \(XSD\)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)   
 [Asignar restricciones de esquema XML \(XSD\) a las restricciones de DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)   
 [Proveedores administrados de ADO.NET y centro de desarrolladores de conjuntos de datos](http://go.microsoft.com/fwlink/?LinkId=217917)