---
title: Cargar información del esquema de un conjunto de datos desde XML
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 43dfb23b-5cef-46f2-8d87-78f0fba1eb8c
ms.openlocfilehash: 69994c546fea842ffef1c8c43d6d6f5bc35e0629
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151057"
---
# <a name="loading-dataset-schema-information-from-xml"></a>Cargar información del esquema de un conjunto de datos desde XML
El esquema <xref:System.Data.DataSet> de un (sus tablas, columnas, relaciones y restricciones) se puede definir <xref:System.Data.Common.DataAdapter>mediante programación, creado por el **Fill** o **FillSchema** métodos de un , o cargado desde un documento XML. Para cargar información de esquema **DataSet** desde un documento XML, puede utilizar el método **ReadXmlSchema** o **InferXmlSchema** del **dataSet**. **ReadXmlSchema** permite cargar o inferir información de esquema **DataSet** del documento que contiene el esquema del lenguaje de definición de esquemas XML (XSD) o un documento XML con esquema XML en línea. **InferXmlSchema** permite deducir el esquema del documento XML mientras se ignoran determinados espacios de nombres XML que especifique.  
  
> [!NOTE]
> Es posible que el orden de tablas en un **dataSet** no se conserve cuando se usan servicios web o serialización XML para transferir un **dataset** que se creó en memoria mediante construcciones XSD (como relaciones anidadas). Por lo tanto, el destinatario del **dataSet** no debe depender del orden de la tabla en este caso. Sin embargo, el orden de tablas siempre se conserva si el esquema del **conjunto** de datos que se transfiere se leyó desde archivos XSD, en lugar de crearse en memoria.  
  
## <a name="readxmlschema"></a>ReadXmlSchema  
 Para cargar el esquema de un **DataSet** desde un documento XML sin cargar ningún dato, puede utilizar el método **ReadXmlSchema** del **conjunto de datos**. **ReadXmlSchema** crea el esquema **DataSet** definido mediante el esquema del lenguaje de definición de esquemas XML (XSD).  
  
 El **ReadXmlSchema** método toma un único argumento de un nombre de archivo, una secuencia o un **XmlReader** que contiene el documento XML que se va a cargar. El documento XML puede contener únicamente el esquema o puede contener el esquema alineado con elementos XML que contienen datos. Para obtener más información sobre cómo escribir el esquema en línea como esquema XML, vea Derivar la estructura relacional del conjunto de datos desde el [esquema XML (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md).  
  
 Si el documento XML pasado a **ReadXmlSchema** no contiene información de esquema en línea, **ReadXmlSchema** deducirá el esquema de los elementos del documento XML. Si el **DataSet** ya contiene un esquema, el esquema actual se ampliará agregando nuevas tablas si aún no existen. En las tablas existentes no se agregarán nuevas columnas. Si una columna que se agrega ya existe en el **conjunto** de datos pero tiene un tipo incompatible con la columna que se encuentra en el XML, se produce una excepción. Para obtener más información sobre cómo **ReadXmlSchema** deduce un esquema de un documento XML, vea [Inferir](inferring-dataset-relational-structure-from-xml.md)estructura relacional de conjunto de datos de XML .  
  
 Aunque **ReadXmlSchema** carga o deduce solo el esquema de un **DataSet**, el **ReadXml** método de la **DataSet** carga o deduce tanto el esquema y los datos contenidos en el documento XML. Para obtener más información, consulte [Carga de un conjunto](loading-a-dataset-from-xml.md)de datos desde XML .  
  
 En los ejemplos de código siguientes se muestra cómo cargar un esquema **DataSet** desde un documento o secuencia XML. En el primer ejemplo se muestra un nombre de archivo de esquema XML que se pasa a la **ReadXmlSchema** método. En el segundo ejemplo se muestra un **archivo System.IO.StreamReader**.  
  
```vb  
Dim dataSet As DataSet = New DataSet  
dataSet.ReadXmlSchema("schema.xsd")  
```  
  
```csharp  
DataSet dataSet = new DataSet();  
dataSet.ReadXmlSchema("schema.xsd");  
```  
  
```vb  
Dim xmlStream As New System.IO.StreamReader("schema.xsd")
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
 También puede indicar al **DataSet** que deduzca su esquema de un documento XML mediante el método **InferXmlSchema** del **conjunto de datos**. **InferXmlSchema** funciona igual que **ReadXml** con un **XmlReadMode** de **InferSchema** (carga datos, así como deduce el esquema) y **ReadXmlSchema** si el documento que se lee no contiene ningún esquema en línea. Sin embargo, **InferXmlSchema** proporciona la capacidad adicional de permitirle especificar espacios de nombres XML concretos que se omitirán cuando se infiere el esquema. **InferXmlSchema** toma dos argumentos necesarios: la ubicación del documento XML, especificada por un nombre de archivo, una secuencia o un **XmlReader**; y una matriz de cadenas de espacios de nombres XML que la operación omitirá.  
  
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
  
 Debido a los atributos especificados para los elementos del documento XML anterior, tanto el método **ReadXmlSchema** como el método **ReadXml** con un **XmlReadMode** de **InferSchema** crearían tablas para cada elemento del documento: **Categories**, **CategoryID**, **CategoryName**, **Description**, **Products**, **ProductID**, **ReorderLevel**y **Discontinued**. (Para obtener más información, consulte [Inferir](inferring-dataset-relational-structure-from-xml.md)estructura relacional de conjunto de datos desde XML .) Sin embargo, una estructura más adecuada sería crear solo las **tablas Categories** y **Products** y, a continuación, crear las columnas **CategoryID**, **CategoryName**y **Description** en las columnas **Categories** y **ProductID**, **ReorderLevel**y **Discontinued** en la tabla **Products.** Para asegurarse de que el esquema deducido omite los atributos especificados en los elementos XML, utilice el método **InferXmlSchema** y especifique el espacio de nombres XML para **officedata** que se omitirá, como se muestra en el ejemplo siguiente.  
  
```vb  
Dim dataSet As DataSet = New DataSet  
dataSet.InferXmlSchema("input_od.xml", New String() {"urn:schemas-microsoft-com:officedata"})  
```  
  
```csharp  
DataSet dataSet = new DataSet();  
dataSet.InferXmlSchema("input_od.xml", new string[] "urn:schemas-microsoft-com:officedata");  
```  
  
## <a name="see-also"></a>Consulte también

- [Usar XML en un conjunto de datos](using-xml-in-a-dataset.md)
- [Derivar una estructura relacional de un conjunto de datos a partir de un esquema XML (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md)
- [Inferir una estructura relacional de un conjunto de datos a partir de XML](inferring-dataset-relational-structure-from-xml.md)
- [Carga de un conjunto de datos desde XML](loading-a-dataset-from-xml.md)
- [Objetos DataSet, DataTable y DataView](index.md)
- [Información general de ADO.NET](../ado-net-overview.md)
