---
title: Derivar una estructura relacional de un conjunto de datos a partir de un esquema XML (XSD)
ms.date: 03/30/2017
ms.assetid: 8f6cd04d-6197-4bc4-9096-8c51c7e4acae
ms.openlocfilehash: d15aa02b41b9a34b00298aeb32d2e3998de8feba
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70786338"
---
# <a name="deriving-dataset-relational-structure-from-xml-schema-xsd"></a>Derivar una estructura relacional de un conjunto de datos a partir de un esquema XML (XSD)
Esta sección ofrece información general sobre cómo se crea el esquema relacional de un `DataSet` a partir del documento de esquema del lenguaje de definición de esquema XML (XSD). En general, para cada `complexType` elemento secundario de un elemento de esquema, se genera una tabla `DataSet`en. La estructura de la tabla está determinada por la definición del tipo complejo. Las tablas se crean en `DataSet` para los elementos de nivel superior del esquema. Sin embargo, solo se crea una tabla para un elemento de `complexType` nivel superior cuando `complexType` el elemento está anidado dentro `complexType` de otro `complexType` elemento, en cuyo caso el elemento anidado se asigna `DataTable` a un `DataSet`dentro de.  
  
 Para obtener más información acerca de XSD, vea el esquema XML de [World Wide Web Consortium (W3C) parte 0: Recomendación](https://www.w3.org/TR/xmlschema-0/)básica, la parte [1 del esquema XML: Recomendación](https://www.w3.org/TR/xmlschema-1/)de estructuras y el [esquema XML parte 2: Datatypes Recommendation](https://www.w3.org/TR/xmlschema-2/) (Parte 2 del esquema XML: recomendación de tipos de datos) del W3C.  
  
 En el ejemplo siguiente se muestra un esquema `customers` XML donde es el elemento secundario `MyDataSet` del elemento, que es un elemento **DataSet** .  
  
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
> Si el elemento `customers` es de un tipo de datos de esquema XML simple como **Integer**, no se genera ninguna tabla. Solo se crean tablas para elementos de nivel superior que sean de tipos complejos.  
  
 En el siguiente esquema XML, el elemento **Schema** tiene dos elementos secundarios, `InStateCustomers` y `OutOfStateCustomers`.  
  
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
  
 Los dos elementos secundarios `InStateCustomers` y `OutOfStateCustomers` son elementos de tipo complejo (`customerType`). Por lo tanto, el proceso de asignación genera las dos siguientes tablas `DataSet`idénticas en.  
  
```  
InStateCustomers (CustomerID , CompanyName, Phone)  
OutOfStateCustomers (CustomerID , CompanyName, Phone)  
```  
  
## <a name="in-this-section"></a>En esta sección  
 [Asignación de restricciones de un esquema XML (XSD) a restricciones de conjuntos de datos](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 Describe los elementos de esquema XML utilizados para crear restricciones de clave única y externa en `DataSet`.  
  
 [Generación de relaciones de objetos DataSet en un esquema XML (XSD)](generating-dataset-relations-from-xml-schema-xsd.md)  
 Describe los elementos de esquema XML utilizados para crear relaciones entre las columnas de `DataSet`la tabla en un.  
  
 [Restricciones y relaciones del esquema XML](xml-schema-constraints-and-relationships.md)  
 Describe cómo se crean implícitamente las relaciones al utilizar elementos de esquema XML para crear restricciones en un `DataSet`.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Usar XML en un conjunto de datos](using-xml-in-a-dataset.md)  
 Describe cómo cargar y conservar la estructura relacional y los datos de `DataSet` como datos XML.  
  
## <a name="see-also"></a>Vea también

- [Información general sobre ADO.NET](../ado-net-overview.md)
