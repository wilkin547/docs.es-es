---
title: Cargar información del esquema de un conjunto de datos desde XML
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 43dfb23b-5cef-46f2-8d87-78f0fba1eb8c
ms.openlocfilehash: a076dcbbe79a7ec0dfbd727e0d0c752bd4675eef
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43515987"
---
# <a name="loading-dataset-schema-information-from-xml"></a>Cargar información del esquema de un conjunto de datos desde XML
El esquema de un <xref:System.Data.DataSet> (sus tablas, columnas, relaciones y restricciones) se pueden definir mediante programación, creado por el **rellenar** o **FillSchema** métodos de un <xref:System.Data.Common.DataAdapter>, o la carga desde un Documento XML. Para cargar **conjunto de datos** información del esquema de un documento XML, puede usar el **ReadXmlSchema** o el **InferXmlSchema** método de la **delconjuntodedatos**. **ReadXmlSchema** le permite cargar o deducir **DataSet** información del esquema del documento que contiene los esquema (XSD) o un documento XML con un esquema XML alineado. **InferXmlSchema** le permite deducir el esquema del documento XML y pasar por alto determinados espacios de nombres XML que especifique.  
  
> [!NOTE]
>  Orden de las tablas una **DataSet** podría no conservarse, al usar servicios Web o serialización XML para transferir un **DataSet** que se creó en memoria mediante construcciones XSD (como las relaciones anidadas). Por lo tanto, el destinatario de la **DataSet** no deben depender orden de las tablas en este caso. Sin embargo, orden de las tablas siempre se mantiene si el esquema de la **DataSet** que se transfiere se recupera de los archivos XSD, en lugar de crearse en memoria.  
  
## <a name="readxmlschema"></a>ReadXmlSchema  
 Para cargar el esquema de un **DataSet** desde un documento XML sin cargar ningún dato, puede usar el **ReadXmlSchema** método de la **DataSet**. **ReadXmlSchema** crea **DataSet** esquema definido mediante el esquema (XSD).  
  
 El **ReadXmlSchema** método toma un único argumento de un nombre de archivo, una secuencia o un **XmlReader** que contiene el documento XML se va a cargar. El documento XML puede contener únicamente el esquema o puede contener el esquema alineado con elementos XML que contienen datos. Para obtener más información sobre cómo escribir esquemas alineados como esquemas XML, vea [derivar estructura relacional de DataSet de esquemas XML (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md).  
  
 Si el documento XML pasado a **ReadXmlSchema** no contiene ninguna información de esquema en línea, **ReadXmlSchema** deducirá el esquema de los elementos en el documento XML. Si el **DataSet** ya contiene un esquema, se extenderá el esquema actual mediante la adición de nuevas tablas si aún no existen. En las tablas existentes no se agregarán nuevas columnas. Si una columna que se va a agregar ya existe en el **DataSet** aunque tiene un tipo incompatible con la columna en el XML, se produce una excepción. Para obtener más información acerca de cómo **ReadXmlSchema** deduce un esquema a partir de un documento XML, vea [deducir el conjunto de datos relacional estructura de XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md).  
  
 Aunque **ReadXmlSchema** carga o deduce únicamente el esquema de un **DataSet**, el **ReadXml** método de la **DataSet** carga o deduce ambos el esquema y los datos contenidos en el documento XML. Para obtener más información, consulte [cargar DataSet desde XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md).  
  
 Los ejemplos de código siguiente muestran cómo cargar un **DataSet** esquema a partir de un documento o secuencia XML. El primer ejemplo muestra un nombre de archivo de esquema XML que se pasan a la **ReadXmlSchema** método. El segundo ejemplo se muestra un **System.IO.StreamReader**.  
  
```vb  
Dim dataSet As DataSet = New DataSet  
dataSet.ReadXmlSchema("schema.xsd")  
```  
  
```csharp  
DataSet dataSet = new DataSet();  
dataSet.ReadXmlSchema("schema.xsd");  
```  
  
```vb  
Dim xmlStream As System.IO.StreamReader = New System.IO.StreamReader ("schema.xsd");  
Dim dataSet As DataSet = New DataSet  
dataSet.ReadXmlSchema(xmlStream)  
xmlStream.Close()  
```  
  
```csharp  
System.IO.StreamReader xmlStream = new System.IO.StreamReader("schema.xsd");  
DataSet dataSet = new DataSet();  
dataSet.ReadXmlSchema(xmlStream);  
xmlStream.Close();  
```  
  
## <a name="inferxmlschema"></a>InferXmlSchema  
 También puede indicar el **conjunto de datos** que deduzca su esquema de un documento XML utilizando el **InferXmlSchema** método de la **conjunto de datos**. **InferXmlSchema** funciona del mismo modo que **ReadXml** con un **XmlReadMode** de **InferSchema** (carga los datos, así como deduce el esquema) y **ReadXmlSchema** si el documento que se está leyendo no contiene ningún esquema alineado. Sin embargo, **InferXmlSchema** ofrece la posibilidad adicional de lo que le permite especificar espacios de nombres XML determinado se omita cuando se deduce el esquema. **InferXmlSchema** toma dos argumentos necesarios: la ubicación del documento XML, especificado por un nombre de archivo, una secuencia o un **XmlReader**; y una matriz de cadenas de espacios de nombres XML para omitir la operación.  
  
 Por ejemplo, tomemos el siguiente código XML:  
  
```xml  
<NewDataSet xmlns:od="urn:schemas-microsoft-com:officedata">  
<Categories>  
  <CategoryID od:adotype="3">1</CategoryID>   
  <CategoryName od:maxLength="15" od:adotype="130">Beverages</CategoryName>   
  <Description od:adotype="203">Soft drinks and teas</Description>   
</Categories>  
<Products>  
  <ProductID od:adotype="20">1</ProductID>   
  <ReorderLevel od:adotype="3">10</ReorderLevel>   
  <Discontinued od:adotype="11">0</Discontinued>   
</Products>  
</NewDataSet>  
```  
  
 Debido a los atributos especificados para los elementos en el documento XML anterior, tanto el **ReadXmlSchema** método y el **ReadXml** método con un **XmlReadMode** de **InferSchema** crean tablas para todos los elementos del documento: **categorías**, **CategoryID**, **CategoryName**, **Descripción**, **productos**, **ProductID**, **ReorderLevel**, y **discontinuo**. (Para obtener más información, consulte [deducir el conjunto de datos relacional estructura de XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md).) Sin embargo, una estructura más adecuada sería crear únicamente la **categorías** y **productos** tablas y, después, crear **CategoryID**, **CategoryName** , y **descripción** columnas en el **categorías** tabla, y **ProductID**, **ReorderLevel**, y **Discontinued** columnas en el **productos** tabla. Para asegurarse de que el esquema inferido pasa por alto los atributos especificados en los elementos XML, utilice el **InferXmlSchema** método y especifique el espacio de nombres XML **officedata** se pasará por alto, como se muestra en el ejemplo siguiente.  
  
```vb  
Dim dataSet As DataSet = New DataSet  
dataSet.InferXmlSchema("input_od.xml", New String() {"urn:schemas-microsoft-com:officedata"})  
```  
  
```csharp  
DataSet dataSet = new DataSet();  
dataSet.InferXmlSchema("input_od.xml", new string[] "urn:schemas-microsoft-com:officedata");  
```  
  
## <a name="see-also"></a>Vea también  
 [Usar XML en un conjunto de datos](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [Derivación de una estructura relacional de un conjunto de datos a partir de un esquema XML (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 [Inferencia de una estructura relacional de un conjunto de datos a partir de XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 [Carga de un conjunto de datos desde XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [Objetos DataSet, DataTable y DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](https://go.microsoft.com/fwlink/?LinkId=217917)
