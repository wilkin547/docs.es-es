---
title: Derivar una estructura relacional de un conjunto de datos a partir de un esquema XML (XSD)
ms.date: 03/30/2017
ms.assetid: 8f6cd04d-6197-4bc4-9096-8c51c7e4acae
ms.openlocfilehash: d32b5cb86bc5a138f9a5f438629d8e231be4ba94
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151174"
---
# <a name="deriving-dataset-relational-structure-from-xml-schema-xsd"></a>Derivar una estructura relacional de un conjunto de datos a partir de un esquema XML (XSD)
Esta sección ofrece información general sobre cómo se crea el esquema relacional de un `DataSet` a partir del documento de esquema del lenguaje de definición de esquema XML (XSD). En general, `complexType` para cada elemento secundario de un elemento `DataSet`de esquema, se genera una tabla en el archivo . La estructura de la tabla está determinada por la definición del tipo complejo. Las tablas `DataSet` se crean en los elementos de nivel superior del esquema. Sin embargo, una tabla solo `complexType` se crea `complexType` para un `complexType` elemento de nivel superior `complexType` cuando el `DataTable` elemento `DataSet`está anidado dentro de otro elemento, en cuyo caso el elemento anidado se asigna a un archivo .  
  
 Para obtener más información sobre el XSD, vea el World Wide Web Consortium (W3C) [XML Schema Part 0: Primer Recommendation](https://www.w3.org/TR/xmlschema-0/), el XML Schema Part [1: Structures Recommendation](https://www.w3.org/TR/xmlschema-1/)y el XML Schema Part [2: Datatypes Recommendation](https://www.w3.org/TR/xmlschema-2/).  
  
 En el ejemplo siguiente se `customers` muestra un esquema `MyDataSet` XML donde es el elemento secundario del elemento, que es un **DataSet** elemento.  
  
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
  
```text  
Customers (CustomerID, CompanyName, Phone)  
```  
  
 El tipo de datos de cada columna de la tabla se deriva del tipo de esquema XML del correspondiente elemento o atributo especificado.  
  
> [!NOTE]
> Si el `customers` elemento es de un tipo de datos de esquema XML simple como **entero**, no se genera ninguna tabla. Solo se crean tablas para elementos de nivel superior que sean de tipos complejos.  
  
 En el esquema XML siguiente, el elemento `InStateCustomers` `OutOfStateCustomers` **Schema** tiene dos elementos secundarios y .  
  
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
  
 Los dos elementos secundarios `InStateCustomers` y `OutOfStateCustomers` son elementos de tipo complejo (`customerType`). Por lo tanto, el proceso de `DataSet`asignación genera las dos tablas idénticas siguientes en el archivo .  
  
```text  
InStateCustomers (CustomerID, CompanyName, Phone)  
OutOfStateCustomers (CustomerID, CompanyName, Phone)  
```  
  
## <a name="in-this-section"></a>En esta sección  
 [Asignar restricciones de un esquema XML (XSD) a restricciones de conjuntos de datos](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 Describe los elementos de esquema XML utilizados para `DataSet`crear restricciones de clave únicas y externas en un archivo .  
  
 [Generación de relaciones de objetos DataSet en un esquema XML (XSD)](generating-dataset-relations-from-xml-schema-xsd.md)  
 Describe los elementos de esquema XML utilizados `DataSet`para crear relaciones entre columnas de tabla en un archivo .  
  
 [Restricciones y relaciones del esquema XML](xml-schema-constraints-and-relationships.md)  
 Describe cómo se crean las relaciones implícitamente cuando se `DataSet`utilizan elementos de esquema XML para crear restricciones en un archivo .  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Usar XML en un conjunto de datos](using-xml-in-a-dataset.md)  
 Describe cómo cargar y conservar la estructura `DataSet` relacional y los datos en datos como XML.  
  
## <a name="see-also"></a>Consulte también

- [Información general de ADO.NET](../ado-net-overview.md)
