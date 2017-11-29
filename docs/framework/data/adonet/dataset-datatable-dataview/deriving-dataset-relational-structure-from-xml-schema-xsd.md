---
title: Derivar una estructura relacional de un conjunto de datos a partir de un esquema XML (XSD)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8f6cd04d-6197-4bc4-9096-8c51c7e4acae
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 0aae23c295401d4b9565c35d4d47c5ab913029d5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="deriving-dataset-relational-structure-from-xml-schema-xsd"></a>Derivar una estructura relacional de un conjunto de datos a partir de un esquema XML (XSD)
Esta sección ofrece información general sobre cómo se crea el esquema relacional de un `DataSet` a partir del documento de esquema del lenguaje de definición de esquema XML (XSD). En general, para cada `complexType` elemento secundario de un elemento de esquema, se genera una tabla en la `DataSet`. La estructura de la tabla está determinada por la definición del tipo complejo. Se crean tablas en el `DataSet` para elementos de nivel superior en el esquema. Sin embargo, solo se crea una tabla para un nivel superior `complexType` elemento cuando el `complexType` elemento está anidado dentro de otro `complexType` elemento, en el que caso anidado `complexType` elemento se asigna a un `DataTable` dentro de la `DataSet`.  
  
 Para obtener más información sobre el XSD, vea World Wide Web Consortium (W3C) XML Schema Part 0: Primer Recommendation, XML Schema Part 1: recomendación de estructuras y XML Schema Part 2: Datatypes Recommendation, ubicado en [http:// www.w3.org/](http://www.w3.org/TR/).  
  
 En el ejemplo siguiente se muestra un esquema XML donde `customers` es el elemento secundario de la `MyDataSet` elemento, que es un **conjunto de datos** elemento.  
  
```xml  
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
  
 En el ejemplo anterior, `customers` es un elemento de tipo complejo. Por tanto, se analiza la definición del tipo complejo y el proceso de asignación crea la tabla siguiente.  
  
```  
Customers (CustomerID , CompanyName, Phone)  
```  
  
 El tipo de datos de cada columna de la tabla se deriva del tipo de esquema XML del correspondiente elemento o atributo especificado.  
  
> [!NOTE]
>  Si el elemento `customers` es de un tipo de datos simple de esquema XML como **entero**, se generará ninguna tabla. Solo se crean tablas para elementos de nivel superior que sean de tipos complejos.  
  
 En el siguiente esquema XML, el **esquema** elemento tiene dos elementos secundarios, `InStateCustomers` y `OutOfStateCustomers`.  
  
```xml  
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
  
 Los dos elementos secundarios `InStateCustomers` y `OutOfStateCustomers` son elementos de tipo complejo (`customerType`). Por lo tanto, el proceso de asignación genera las dos siguientes tablas idénticas en el `DataSet`.  
  
```  
InStateCustomers (CustomerID , CompanyName, Phone)  
OutOfStateCustomers (CustomerID , CompanyName, Phone)  
```  
  
## <a name="in-this-section"></a>En esta sección  
 [Asignar restricciones de esquema (XSD) de XML a las restricciones de conjunto de datos](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 Describe los elementos de esquema XML utilizados para crear restricciones de clave únicas y externas en un `DataSet`.  
  
 [Generar las relaciones de conjunto de datos desde un esquema XML (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)  
 Describe los elementos de esquema XML utilizados para crear relaciones entre columnas de tabla en un `DataSet`.  
  
 [Las relaciones y restricciones de esquema XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/xml-schema-constraints-and-relationships.md)  
 Describe cómo se crean implícitamente relaciones cuando se utilizan elementos de esquema XML para crear restricciones en un `DataSet`.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Usar XML en un conjunto de datos](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 Describe cómo cargar y hacer persistentes la estructura relacional y los datos en un `DataSet` como datos XML.  
  
## <a name="see-also"></a>Vea también  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)
