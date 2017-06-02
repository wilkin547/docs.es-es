---
title: "Derivar la estructura relacional de DataSet desde la definici&#243;n de esquema XML (XSD) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8f6cd04d-6197-4bc4-9096-8c51c7e4acae
caps.latest.revision: 5
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Derivar la estructura relacional de DataSet desde la definici&#243;n de esquema XML (XSD)
Esta sección ofrece información general sobre cómo se crea el esquema relacional de un <xref:System.Data.DataSet> a partir del documento de esquema del lenguaje de definición de esquema XML \(XSD\).  En general, para cada elemento secundario **complexType** de un elemento del esquema se genera una tabla en el **DataSet**.  La estructura de la tabla está determinada por la definición del tipo complejo.  Se crean tablas en el **DataSet** para los elementos de nivel superior del esquema.  Sin embargo, solo se crea una tabla para un elemento **complexType** de nivel superior cuando el elemento **complexType** está anidado dentro de otro elemento **complexType**, en cuyo caso el elemento **complexType** anidado se asigna a una <xref:System.Data.DataTable> dentro del **DataSet**.  
  
 Para obtener más información sobre el XSD, vea los siguientes temas del consorcio W3C, XML Schema Part 0: Recomendación base del esquema XML, XML Schema Part 1: Recomendación de estructuras y XML Schema Part 2: Recomendación sobre tipos de datos, en la dirección [http:\/\/www.w3.org\/](http://www.w3.org/TR/).  
  
 En el siguiente ejemplo se muestra un esquema XML donde `customers` es el elemento secundario del elemento `MyDataSet`, que es un elemento **DataSet**.  
  
```  
<xs:schema id="SomeID"   
            xmlns=""   
            xmlns:xs="http://www.w3.org/2001/XMLSchema"   
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
   <xs:element name="MyDataSet" msdata:IsDataSet="true">  
     <xs:complexType>  
       <xs:choice maxOccurs="unbounded">  
         <xs:element name="customers" >   
           <xs:complexType >  
             <xs:sequence>  
               <xs:element name="CustomerID" type="xs:integer"   
                            minOccurs="0" />  
               <xs:element name="CompanyName" type="xs:string"   
                            minOccurs="0" />  
               <xs:element name="Phone" type="xs:string" />  
             </xs:sequence>  
           </xs:complexType>  
          </xs:element>  
       </xs:choice>  
     </xs:complexType>  
   </xs:element>  
 </xs:schema>  
```  
  
 En el ejemplo anterior, `customers` es un elemento de tipo complejo.  Por tanto, se analiza la definición del tipo complejo y el proceso de asignación crea la tabla siguiente.  
  
```  
Customers (CustomerID , CompanyName, Phone)  
```  
  
 El tipo de datos de cada columna de la tabla se deriva del tipo de esquema XML del correspondiente elemento o atributo especificado.  
  
> [!NOTE]
>  Si el elemento `customers` es de un tipo de datos simple de esquema XML como **integer**, no se generará ninguna tabla.  Solo se crean tablas para elementos de nivel superior que sean de tipos complejos.  
  
 En el siguiente esquema XML, el elemento **Schema** tiene dos elementos secundarios: `InStateCustomers` y `OutOfStateCustomers`.  
  
```  
<xs:schema id="SomeID"   
            xmlns=""   
            xmlns:xs="http://www.w3.org/2001/XMLSchema"   
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
   <xs:element name="InStateCustomers" type="customerType" />  
   <xs:element name="OutOfStateCustomers" type="customerType" />  
    <xs:complexType name="customerType" >  
  
     </xs:complexType>  
  
   <xs:element name="MyDataSet" msdata:IsDataSet="true">  
     <xs:complexType>  
       <xs:choice maxOccurs="unbounded">  
         <xs:element ref="customers" />  
       </xs:choice>  
     </xs:complexType>  
   </xs:element>  
 </xs:schema>  
```  
  
 Los dos elementos secundarios `InStateCustomers` y `OutOfStateCustomers` son elementos de tipo complejo \(`customerType`\).  Por tanto, el proceso de asignación genera las dos siguientes tablas idénticas en el **DataSet**.  
  
```  
InStateCustomers (CustomerID , CompanyName, Phone)  
OutOfStateCustomers (CustomerID , CompanyName, Phone)  
```  
  
## En esta sección  
 [Asignar restricciones de esquema XML \(XSD\) a las restricciones de DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 Describe los elementos de esquema XML utilizados para crear restricciones de clave única y externa en un **DataSet**.  
  
 [Generar las relaciones de DataSet desde la definición de esquemas XML \(XSD\)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)  
 Describe los elementos de esquema XML utilizados para crear relaciones entre columnas de tabla de un **DataSet**.  
  
 [Restricciones y relaciones de esquemas XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/xml-schema-constraints-and-relationships.md)  
 Describe cómo se crean implícitamente relaciones cuando se utilizan elementos de esquema XML para crear restricciones en un **DataSet**.  
  
## Secciones relacionadas  
 [Utilizar XML en un DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 Describe cómo cargar y hacer persistentes la estructura relacional y los datos de un **DataSet** como datos XML.  
  
## Vea también  
 [Proveedores administrados de ADO.NET y centro de desarrolladores de conjuntos de datos](http://go.microsoft.com/fwlink/?LinkId=217917)