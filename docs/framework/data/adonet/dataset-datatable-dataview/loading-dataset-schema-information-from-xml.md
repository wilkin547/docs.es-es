---
title: Cargar información del esquema de un conjunto de datos desde XML
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 43dfb23b-5cef-46f2-8d87-78f0fba1eb8c
ms.openlocfilehash: b084590d7158024227a9f12da759b56ae2031373
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201348"
---
# <a name="loading-dataset-schema-information-from-xml"></a>Cargar información del esquema de un conjunto de datos desde XML

El esquema de un <xref:System.Data.DataSet> (sus tablas, columnas, relaciones y restricciones) se puede definir mediante programación, lo crean los métodos **Fill** o **FillSchema** de un <xref:System.Data.Common.DataAdapter> , o se cargan desde un documento XML. Para cargar información de esquema de **conjunto** de datos desde un documento XML, puede usar los métodos **ReadXmlSchema** o **InferXmlSchema** del **conjunto**de datos. **ReadXmlSchema** permite cargar o deducir información del esquema del **conjunto** de datos del documento que contiene el esquema del lenguaje de definición de esquemas XML (XSD) o un documento XML con un esquema XML alineado. **InferXmlSchema** permite deducir el esquema del documento XML mientras se omiten determinados espacios de nombres XML que se especifiquen.  
  
> [!NOTE]
> Es posible que el orden de las tablas en un **conjunto** de objetos no se conserve cuando se utilizan los servicios web o la serialización XML para transferir un **DataSet** que se creó en memoria mediante construcciones xsd (como las relaciones anidadas). Por lo tanto, el destinatario del **conjunto de DataSet** no debe depender de la ordenación de la tabla en este caso. Sin embargo, el orden de las tablas siempre se conserva si el esquema del conjunto de los **conjuntos** de archivos que se va a transferir se leyó desde archivos XSD, en lugar de crearse en memoria.  
  
## <a name="readxmlschema"></a>ReadXmlSchema  

 Para cargar el esquema de un **DataSet** desde un documento XML sin cargar ningún dato, puede usar el método **ReadXmlSchema** del **conjunto**de datos. **ReadXmlSchema** crea un esquema de **conjunto de DataSet** definido mediante el esquema del lenguaje de definición de esquemas XML (XSD).  
  
 El método **ReadXmlSchema** toma un solo argumento de un nombre de archivo, una secuencia o un **XmlReader** que contiene el documento XML que se va a cargar. El documento XML puede contener únicamente el esquema o puede contener el esquema alineado con elementos XML que contienen datos. Para obtener más información sobre cómo escribir esquemas insertados como esquemas XML, vea [derivar una estructura relacional de conjunto de datos a partir de un esquema XML (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md).  
  
 Si el documento XML pasado a **ReadXmlSchema** no contiene información de esquema insertado, **ReadXmlSchema** deducirá el esquema a partir de los elementos del documento XML. Si el **conjunto** de contenido ya contiene un esquema, el esquema actual se extenderá agregando nuevas tablas si aún no existen. En las tablas existentes no se agregarán nuevas columnas. Si una columna que se va a agregar ya existe en el **conjunto de DataSet** pero tiene un tipo incompatible con la columna que se encuentra en el XML, se produce una excepción. Para obtener más información sobre cómo **ReadXmlSchema** deduce un esquema a partir de un documento XML, vea [inferir la estructura relacional de DataSet desde XML](inferring-dataset-relational-structure-from-xml.md).  
  
 Aunque **ReadXmlSchema** carga o deduce solo el esquema de un **DataSet**, el método **ReadXml** del **conjunto** de datos carga o deduce el esquema y los datos contenidos en el documento XML. Para obtener más información, vea [cargar un conjunto de datos desde XML](loading-a-dataset-from-xml.md).  
  
 En los siguientes ejemplos de código se muestra cómo cargar un esquema de **DataSet** desde un documento o una secuencia XML. En el primer ejemplo se muestra un nombre de archivo de esquema XML que se pasa al método **ReadXmlSchema** . En el segundo ejemplo se muestra **System. IO. StreamReader**.  
  
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

 También puede indicar al **conjunto de DataSet** que infiera su esquema a partir de un documento XML mediante el método **InferXmlSchema** del **conjunto**de información. **InferXmlSchema** funciona igual que los dos **ReadXml** con un **XmlReadMode** de **InferSchema** (carga los datos, así como deduces) y **ReadXmlSchema** si el documento que se lee no contiene ningún esquema en línea. Sin embargo, **InferXmlSchema** proporciona la capacidad adicional de permitirle especificar espacios de nombres XML determinados que se omitirán cuando se infiera el esquema. **InferXmlSchema** acepta dos argumentos necesarios: la ubicación del documento XML, especificada por un nombre de archivo, una secuencia o un **XmlReader**; y una matriz de cadena de espacios de nombres XML que la operación pasará por alto.  
  
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
  
 Debido a los atributos especificados para los elementos del documento XML anterior, tanto el método **ReadXmlSchema** como el **método ReadXml** con un **XmlReadMode** de **InferSchema** crearán tablas para cada elemento del documento: **Categories**, **CategoryID**, **CategoryName**, **Description**, **Products**, **ProductID**, **ReorderLevel**y **Discontinued**. (Para obtener más información, vea [inferir la estructura relacional de DataSet desde XML](inferring-dataset-relational-structure-from-xml.md)). Sin embargo, una estructura más adecuada consistiría en crear únicamente las tablas **Categories** y **Products** y, a continuación, crear las columnas **CategoryID**, **CategoryName**y **Description** en la tabla **Categories** y las columnas **ProductID**, **ReorderLevel**y **Discontinued** en la tabla **Products** . Para asegurarse de que el esquema deducido omite los atributos especificados en los elementos XML, use el método **InferXmlSchema** y especifique el espacio de nombres XML para **officedata** que se va a omitir, como se muestra en el ejemplo siguiente.  
  
```vb  
Dim dataSet As DataSet = New DataSet  
dataSet.InferXmlSchema("input_od.xml", New String() {"urn:schemas-microsoft-com:officedata"})  
```  
  
```csharp  
DataSet dataSet = new DataSet();  
dataSet.InferXmlSchema("input_od.xml", new string[] "urn:schemas-microsoft-com:officedata");  
```  
  
## <a name="see-also"></a>Vea también

- [Usar XML en un conjunto de datos](using-xml-in-a-dataset.md)
- [Derivar una estructura relacional de un conjunto de datos a partir de un esquema XML (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md)
- [Inferir una estructura relacional de un conjunto de datos a partir de XML](inferring-dataset-relational-structure-from-xml.md)
- [Cargar un conjunto de datos desde XML](loading-a-dataset-from-xml.md)
- [Objetos DataSet, DataTable y DataView](index.md)
- [Información general de ADO.NET](../ado-net-overview.md)
