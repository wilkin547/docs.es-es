---
title: Importación del esquema para generar clases
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, schema import and export
- XsdDataContractImporter class
ms.assetid: b9170583-8c34-43bd-97bb-6c0c8dddeee0
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 7fc755ff7f1b6c583a1e9aa1bc209495563812f0
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="importing-schema-to-generate-classes"></a>Importación del esquema para generar clases
Para generar las clases desde los esquemas que se pueden utilizar con [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], utilice la clase <xref:System.Runtime.Serialization.XsdDataContractImporter>. En este tema se describen el proceso y variaciones.  
  
## <a name="the-import-process"></a>El proceso de importación  
 El proceso de importación del esquema se inicia con <xref:System.Xml.Schema.XmlSchemaSet> y genera <xref:System.CodeDom.CodeCompileUnit>.  
  
 `XmlSchemaSet` forma parte del Modelo de objetos de esquemas (SOM) de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] que representa un conjunto de documentos de esquema (XSD) de lenguaje de definición de esquemas XML. Para crear un objeto `XmlSchemaSet` a partir de un conjunto de documentos XSD, deserialice cada documento en un objeto (utilizando el <xref:System.Xml.Schema.XmlSchema>) <xref:System.Xml.Serialization.XmlSerializer> y agregue estos objetos a un nuevo `XmlSchemaSet`.  
  
 `CodeCompileUnit` forma parte del Modelo de objetos de documento (CodeDOM) de Código de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] que representa el código [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] de una manera abstracta. Para generar el código real a partir de `CodeCompileUnit`, utilice una subclase de la clase <xref:System.CodeDom.Compiler.CodeDomProvider>, como <xref:Microsoft.CSharp.CSharpCodeProvider> o la clase <xref:Microsoft.VisualBasic.VBCodeProvider>.  
  
#### <a name="to-import-a-schema"></a>Importar un esquema  
  
1.  Cree una instancia de <xref:System.Runtime.Serialization.XsdDataContractImporter>.  
  
2.  Opcional. Pase `CodeCompileUnit` en el constructor. Los tipos generados durante la importación del esquema se agregan a la instancia `CodeCompileUnit` en lugar de iniciarse con un `CodeCompileUnit`en blanco.  
  
3.  Opcional. Llame a uno de los métodos <xref:System.Runtime.Serialization.XsdDataContractImporter.CanImport%2A>. El método determina si el esquema determinado es un esquema de contrato de datos válido y si se puede importar. El método `CanImport` tiene las mismas sobrecargas que `Import` (el paso siguiente).  
  
4.  Llame a uno de los métodos `Import` sobrecargados, por ejemplo, el método <xref:System.Runtime.Serialization.XsdDataContractImporter.Import%28System.Xml.Schema.XmlSchemaSet%29>.  
  
     La sobrecarga más simple toma `XmlSchemaSet` e importa todos los tipos, incluidos los tipos anónimos, situados en ese esquema establecido. Otras sobrecargas le permiten especificar el tipo XSD o una lista de tipos a importar (en el formulario de <xref:System.Xml.XmlQualifiedName> o una colección de los objetos `XmlQualifiedName` ). En este caso, solo se importan los tipos especificados. Una sobrecarga toma <xref:System.Xml.Schema.XmlSchemaElement> que importa un elemento determinado fuera de `XmlSchemaSet`, así como su tipo asociado (si es anónimo o no). Esta sobrecarga devuelve `XmlQualifiedName`, que representa el nombre de contrato de datos del tipo generado para este elemento.  
  
     Varias llamadas del método `Import` producen como resultado varios elementos que se agregan al mismo `CodeCompileUnit`. Un tipo no se genera en `CodeCompileUnit` si ya existe en este. Llame varias veces `Import` al mismo `XsdDataContractImporter` en lugar de utilizar varios objetos `XsdDataContractImporter`. Ésta es la manera recomendada de evitar que se generen tipos duplicados.  
  
    > [!NOTE]
    >  Si se produce un error durante la importación, `CodeCompileUnit` estará en un estado imprevisible. Si utiliza `CodeCompileUnit` como resultado de una importación en la que se ha producido un error, podría exponerse a vulnerabilidades de seguridad.  
  
5.  Obtenga acceso a `CodeCompileUnit` a través de la propiedad <xref:System.Runtime.Serialization.XsdDataContractImporter.CodeCompileUnit%2A>.  
  
### <a name="import-options-customizing-the-generated-types"></a>Importar opciones: Personalizar los tipos generados  
 Puede establecer la propiedad <xref:System.Runtime.Serialization.XsdDataContractImporter.Options%2A> de <xref:System.Runtime.Serialization.XsdDataContractImporter> a una instancia de la clase <xref:System.Runtime.Serialization.ImportOptions> para administrar varios aspectos del proceso de importación. Hay varias opciones influyen directamente en los tipos generados.  
  
#### <a name="controlling-the-access-level-generateinternal-or-the-internal-switch"></a>Controlar el nivel de acceso (GenerateInternal o el modificador /interno)  
 Esto corresponde a la **/ interno** activar la [la herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).  
  
 Normalmente, los tipos públicos se generan a partir del esquema, con campos privados y propiedades de miembro de datos públicos coincidentes. Para generar tipos internos en su lugar, establezca la propiedad <xref:System.Runtime.Serialization.ImportOptions.GenerateInternal%2A> en `true`.  
  
 El ejemplo siguiente muestra un esquema transformado en una clase interna cuando la propiedad <xref:System.Runtime.Serialization.ImportOptions.GenerateInternal%2A> está establecida en `true.`  
  
 [!code-csharp[c_SchemaImportExport#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/cs/source.cs#2)]
 [!code-vb[c_SchemaImportExport#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_schemaimportexport/vb/source.vb#2)]  
  
#### <a name="controlling-namespaces-namespaces-or-the-namespace-switch"></a>Controlar espacios de nombres (Espacios de nombres o el modificador /espacio de nombres)  
 Esto corresponde a la **/Namespace** activar el `Svcutil.exe` herramienta.  
  
 Normalmente, los tipos generados a partir del esquema se generan en [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] espacios de nombres, con cada espacio de nombres XSD corresponde a un determinado [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] según una asignación descrita en el espacio de nombres [referencia de esquema de contrato de datos](../../../../docs/framework/wcf/feature-details/data-contract-schema-reference.md). Puede personalizar esta asignación mediante la propiedad <xref:System.Runtime.Serialization.ImportOptions.Namespaces%2A> a <xref:System.Collections.Generic.Dictionary%602>. Si se encuentra un espacio de nombres XSD determinado en el diccionario, el espacio de nombres [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] correspondiente también se toma de su diccionario.  
  
 Por ejemplo, considere el siguiente esquema:  
  
 [!code-xml[c_SchemaImportExport#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/common/source.config#10)]  
  
 En el ejemplo siguiente se usa el `Namespaces` propiedad para asignar el "http://schemas.contoso.com/carSchema" espacio de nombres a "Contoso.Cars".  
  
 [!code-csharp[c_SchemaImportExport#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/cs/source.cs#8)]
 [!code-vb[c_SchemaImportExport#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_schemaimportexport/vb/source.vb#8)]  
  
#### <a name="adding-the-serializableattribute-generateserializable-or-the-serializable-switch"></a>Agregar SerializableAttribute (GenerateSerializable o el modificador /serializable)  
 Esto corresponde a la **/ serializable** activar el `Svcutil.exe` herramienta.  
  
 En algunas ocasiones, es importante que los tipos generados a partir del esquema se puedan utilizar con los motores de la serialización en tiempo de ejecución [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] (por ejemplo, <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=nameWithType> y las clases <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> ). Esto es útil cuando se utilizan los tipos para la comunicación remota [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]. Para habilitarlo, debe aplicar el atributo <xref:System.SerializableAttribute> a los tipos generados además del atributo <xref:System.Runtime.Serialization.DataContractAttribute> normal. Se genera el atributo automáticamente si la opción de importación `GenerateSerializable` está establecida en `true`.  
  
 El ejemplo siguiente muestra la clase `Vehicle` generada con la opción establecida de importación `GenerateSerializable` a `true`.  
  
 [!code-csharp[c_SchemaImportExport#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/cs/source.cs#4)]
 [!code-vb[c_SchemaImportExport#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_schemaimportexport/vb/source.vb#4)]  
  
#### <a name="adding-data-binding-support-enabledatabinding-or-the-enabledatabinding-switch"></a>Agregar compatibilidad de enlace de datos (EnableDataBinding o el modificador /enableDataBinding)  
 Esto corresponde a la **/enableDataBinding** cambiar de la herramienta Svcutil.exe.  
  
 Es posible que quiera enlazar los tipos generados a partir del esquema a los componentes de interfaz gráfica de usuario para que las actualizaciones en las instancias de estos tipos se actualicen automáticamente en la Interfaz de usuario. `XsdDataContractImporter` puede generar tipos que implementan la interfaz <xref:System.ComponentModel.INotifyPropertyChanged> de manera que cualquier cambio de propiedad active un evento. Si está generando tipos para su uso con un entorno de programación de la interfaz de usuario de cliente que admite esta interfaz (como Windows Presentation Foundation (WPF)), establezca el <xref:System.Runtime.Serialization.ImportOptions.EnableDataBinding%2A> propiedad `true` para habilitar esta característica.  
  
 El ejemplo siguiente muestra la clase `Vehicle` generada con <xref:System.Runtime.Serialization.ImportOptions.EnableDataBinding%2A> establecida a `true`.  
  
 [!code-csharp[C_SchemaImportExport#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/cs/source.cs#5)]
 [!code-vb[C_SchemaImportExport#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_schemaimportexport/vb/source.vb#5)]  
  
### <a name="import-options-choosing-collection-types"></a>Opciones de importación: Elegir tipos de colección  
 Dos patrones especiales en XML representan colecciones de elementos: listas de elementos y asociaciones entre un elemento y otro. A continuación se muestra un ejemplo de una lista de cadenas:  
  
 [!code-xml[C_SchemaImportExport#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/common/source.config#11)]  
  
 A continuación, se muestra un ejemplo de una asociación entre una cadena y un entero (`city name` y `population`).  
  
 [!code-xml[C_SchemaImportExport#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/common/source.config#12)]  
  
> [!NOTE]
>  Las asociaciones también se podrían considerar una lista. Por ejemplo, puede ver la asociación anterior como una lista de objetos `city` complejos que tienen dos campos (un campo de cadena y un campo de valor entero). Ambos patrones tienen una representación en el Esquema XSD. No hay ningún modo de diferenciar entre una lista y una asociación, así que estos patrones siempre se tratan como listas a menos que haya una anotación especial en el esquema específica para [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. La anotación indica que un patrón determinado representa una asociación. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Referencia de esquema de contrato de datos](../../../../docs/framework/wcf/feature-details/data-contract-schema-reference.md).  
  
 Normalmente, una lista se importa como un contrato de datos de colección derivado de una Lista Genérica o como una matriz [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], según si el esquema sigue el patrón estándar de denominación o no para las colecciones. Esto se describe con más detalle en [tipos de colección en contratos de datos](../../../../docs/framework/wcf/feature-details/collection-types-in-data-contracts.md). Las asociaciones se importan normalmente como <xref:System.Collections.Generic.Dictionary%602> o como un contrato de datos de colección derivado del objeto de diccionario. Por ejemplo, considere el siguiente esquema:  
  
 [!code-xml[c_SchemaImportExport#13](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/common/source.config#13)]  
  
 Esto se importaría como se indica a continuación (se muestran los campos en lugar de las propiedades para facilitar la lectura).  
  
 [!code-csharp[c_SchemaImportExport#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/cs/source.cs#6)]
 [!code-vb[c_SchemaImportExport#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_schemaimportexport/vb/source.vb#6)]  
  
 Se pueden personalizar los tipos de colección generados para estos patrones del esquema. Por ejemplo, puede querer generar colecciones derivadas de <xref:System.ComponentModel.BindingList%601> en lugar de la clase <xref:System.Collections.Generic.List%601> para enlazar el tipo a un cuadro de lista y para que se actualice automáticamente cuando cambien los contenidos de la colección. Para ello, establezca la propiedad <xref:System.Runtime.Serialization.ImportOptions.ReferencedCollectionTypes%2A> de la clase <xref:System.Runtime.Serialization.ImportOptions> en una lista de tipos de colección que se utilizarán (de ahora en adelante conocidos como los tipos con referencia). Cuando se importa una colección, se digitaliza esta lista de tipos de colección con referencia y, si se encuentra uno, se utiliza la colección que mejor coincida. Solamente se comparan asociaciones con tipos que implementan la interfaz genérica o no genérica <xref:System.Collections.IDictionary>, mientras que las listas se comparan con cualquier tipo de colección compatible.  
  
 Por ejemplo, si la propiedad <xref:System.Runtime.Serialization.ImportOptions.ReferencedCollectionTypes%2A> está establecida en <xref:System.ComponentModel.BindingList%601>, el tipo `people` en el ejemplo anterior se genera como se indica a continuación.  
  
 [!code-csharp[C_SchemaImportExport#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/cs/source.cs#7)]
 [!code-vb[C_SchemaImportExport#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_schemaimportexport/vb/source.vb#7)]  
  
 Se considera que un tipo genérico cerrado es el que más coincide. Por ejemplo, si los tipos `BindingList(Of Integer)` y <xref:System.Collections.ArrayList> se pasan a la colección de tipos con referencia, las listas de enteros encontradas en el esquema se importan como `BindingList(Of Integer)`. Cualquier otra lista, por ejemplo, `List(Of String)`, se importa como `ArrayList`.  
  
 Si un tipo que implementa la interfaz `IDictionary` genérica se agrega a la colección de tipos con referencia, sus parámetros de tipo deben estar o totalmente abiertos o totalmente cerrados.  
  
 No se permiten duplicados. Por ejemplo, no puede agregar `List(Of Integer)` sino `Collection(Of Integer)` a los tipos con referencia. Eso haría imposible determinar cuál se debería utilizar cuando una lista de enteros se encuentra en esquema. Los duplicados se detectarán solo si hay un tipo en esquema que expone el problema de los duplicados. Por ejemplo, si el esquema importado no contiene listas de enteros, puede tener `List(Of Integer)` y `Collection(Of Integer)` en la colección de tipos con referencia, pero no tendrán ningún efecto.  
  
 El mecanismo de tipos de colección con referencia funciona igual de bien para las colecciones de tipos complejos (incluso las colecciones de otras colecciones) y no solo para las colecciones de primitivos.  
  
 El `ReferencedCollectionTypes` propiedad se corresponde con el **/collectionType** cambiar de la herramienta SvcUtil.exe. Tenga en cuenta que para hacer referencia a varios tipos de colección, el **/collectionType** conmutador debe especificarse varias veces. Si el tipo no está en MsCorLib.dll, su ensamblado debe también se hace referencia mediante el **/reference** cambiar.  
  
#### <a name="import-options-referencing-existing-types"></a>Opciones de importación: Hacer referencia a tipos existentes  
 De vez en cuando, los tipos en esquema corresponden a los tipos [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] existentes y no es necesario generar estos tipos desde el principio. (Esta sección solo se aplica a los tipos noncollection. Para los tipos de colección, consulte la sección anterior.)  
  
 Por ejemplo, puede tener un tipo de contrato de datos "Persona" estándar para toda la compañía que siempre quiere utilizar cuando represente una persona. Cuando algún servicio utiliza este tipo y su esquema aparece en los metadatos del servicio, puede reutilizar el tipo `Person` existente cuando importe este esquema en lugar de generar uno nuevo para cada servicio.  
  
 Para ello, pase una lista de tipos [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] que quiere reutilizar en la colección que la propiedad <xref:System.Runtime.Serialization.ImportOptions.ReferencedTypes%2A> devuelve en la clase <xref:System.Runtime.Serialization.ImportOptions>. Si alguno de estos tipos tiene un nombre de contrato de datos y espacio de nombres que coincide con el nombre y espacio de nombres de un tipo de esquema, se realiza una comparación estructural. Si se determina que los tipos coinciden en nombres y en estructuras, el tipo [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] existente se reutiliza en lugar de generar uno nuevo. Si solo coincide el nombre y no la estructura, se produce una excepción. Tenga en cuenta que no hay ninguna concesión para controlar las versiones al hacer referencia a tipos (por ejemplo, agregar nuevos miembros de datos opcionales). Las estructuras deben coincidir con exactitud.  
  
 Es legal agregar varios tipos con el mismo nombre de contrato de datos y espacio de nombres a la colección de tipos con referencia, siempre que no se importe ningún tipo de esquema con ese nombre y espacio de nombres. Esto le permite agregar con facilidad todos los tipos en un ensamblado a la colección sin preocuparse por los duplicados para los tipos que realmente no se producen en esquema.  
  
 El `ReferencedTypes` propiedad se corresponde con el **/reference** cambie en ciertos modos de funcionamiento de la herramienta Svcutil.exe.  
  
> [!NOTE]
>  Cuando se utiliza Svcutil.exe o (en [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]) la **Agregar referencia de servicio** herramientas, todos los tipos en MsCorLib.dll automáticamente se hace referencia.  
  
#### <a name="import-options-importing-non-datacontract-schema-as-ixmlserializable-types"></a>Opciones de importación: Importar esquema Non-DataContract como tipos IXmlSerializable  
 <xref:System.Runtime.Serialization.XsdDataContractImporter> admite un subconjunto limitado del esquema. Si las construcciones de esquema no compatibles están presentes (por ejemplo, atributos XML), se produce un error en los intentos de importación y se genera una excepción. Sin embargo, si se establece la propiedad <xref:System.Runtime.Serialization.ImportOptions.ImportXmlType%2A> en `true`,  se extiende el intervalo de esquema compatible. Cuando se establece en `true`, <xref:System.Runtime.Serialization.XsdDataContractImporter> genera tipos que implementan la interfaz <xref:System.Xml.Serialization.IXmlSerializable>. Esto permite el acceso directo a la representación XML de estos tipos.  
  
##### <a name="design-considerations"></a>Consideraciones de diseño  
  
-   Puede ser difícil trabajar directamente con la representación XML con tipos débiles. Considere utilizar un motor de serialización alternativo, como por ejemplo <xref:System.Xml.Serialization.XmlSerializer>, para trabajar con esquema no compatible con contratos de datos fuertemente tipados. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Mediante la clase XmlSerializer](../../../../docs/framework/wcf/feature-details/using-the-xmlserializer-class.md).  
  
-   <xref:System.Runtime.Serialization.XsdDataContractImporter> no puede importar algunas construcciones de esquema incluso cuando la propiedad <xref:System.Runtime.Serialization.ImportOptions.ImportXmlType%2A> está establecida en `true`. De nuevo, considere utilizar <xref:System.Xml.Serialization.XmlSerializer> para estos casos.  
  
-   Las construcciones exactas de esquema que son compatibles cuando <xref:System.Runtime.Serialization.ImportOptions.ImportXmlType%2A> es `true` o `false` se describen en [referencia de esquema de contrato de datos](../../../../docs/framework/wcf/feature-details/data-contract-schema-reference.md).  
  
-   El esquema para tipos <xref:System.Xml.Serialization.IXmlSerializable> generados que no retienen la fidelidad cuando se importan y exportan. Es decir, exportar el esquema a partir de los tipos generados e importar como clases no devuelve el esquema original.  
  
 Es posible combinar la opción <xref:System.Runtime.Serialization.ImportOptions.ImportXmlType%2A> con la opción <xref:System.ServiceModel.Description.ServiceContractGenerator.ReferencedTypes%2A> descrita previamente. Para los tipos que tienen que ser generados como implementaciones <xref:System.Xml.Serialization.IXmlSerializable>, se omite la comprobación estructural cuando se utiliza la característica <xref:System.ServiceModel.Description.ServiceContractGenerator.ReferencedTypes%2A>.  
  
 El <xref:System.Runtime.Serialization.ImportOptions.ImportXmlType%2A> opción se corresponde con el **/importXmlTypes** cambiar de la herramienta Svcutil.exe.  
  
##### <a name="working-with-generated-ixmlserializable-types"></a>Trabajar con tipos generados IXmlSerializable  
 Los tipos `IXmlSerializable` generados contienen un campo privado, denominado "nodesField", que devuelve una matriz de los objetos <xref:System.Xml.XmlNode>. Cuando se deserializa una instancia de este tipo, usted puede tener acceso directamente a los datos XML a través de este campo utilizando el Modelo de objetos del documento XML. Cuando se serializa una instancia de este tipo, usted puede establecer este campo a los datos XML deseados y se serializará.  
  
 Esto se logra a través de la implementación `IXmlSerializable`. En el tipo `IXmlSerializable` generado, la implementación <xref:System.Xml.Serialization.IXmlSerializable.ReadXml%2A> llama al método <xref:System.Runtime.Serialization.XmlSerializableServices.ReadNodes%2A> de la clase <xref:System.Runtime.Serialization.XmlSerializableServices>. El método es un método auxiliar que convierte XML proporcionado a través de <xref:System.Xml.XmlReader> a una matriz de los objetos <xref:System.Xml.XmlNode>. La implementación <xref:System.Xml.Serialization.IXmlSerializable.WriteXml%2A> hace el contrario y convierte la matriz de los objetos `XmlNode` a una secuencia de llamadas <xref:System.Xml.XmlWriter>. Esto se realiza mediante el método <xref:System.Runtime.Serialization.XmlSerializableServices.WriteNodes%2A>.  
  
 Se puede ejecutar el proceso de exportación del esquema en las clases `IXmlSerializable` generadas. Como se ha expresado previamente, no se le devolverá el esquema original. En su lugar, obtendrá el tipo XSD estándar de "anyType", el que es un carácter comodín para cualquier tipo XSD.  
  
 Esto se logra aplicando el <xref:System.Xml.Serialization.XmlSchemaProviderAttribute> atribuir a generado `IXmlSerializable` clases y especificando un método que llama el <xref:System.Runtime.Serialization.XmlSerializableServices.AddDefaultSchema%2A> método para generar el tipo "anyType".  
  
> [!NOTE]
>  El tipo <xref:System.Runtime.Serialization.XmlSerializableServices> existe solamente para admitir esta característica determinada. No se recomienda utilizarlo para cualquier otro propósito.  
  
#### <a name="import-options-advanced-options"></a>Opciones de importación: Opciones avanzadas  
 Estas son opciones de importación avanzadas:  
  
-   Propiedad <xref:System.Runtime.Serialization.ImportOptions.CodeProvider%2A>. Especifique <xref:System.CodeDom.Compiler.CodeDomProvider> que quiere utilizar para generar el código para las clases generadas. El mecanismo de importación intenta evitar características que <xref:System.CodeDom.Compiler.CodeDomProvider> no admite. Si no se establece <xref:System.Runtime.Serialization.ImportOptions.CodeProvider%2A>, el conjunto completo de características de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] se utiliza sin restricciones.  
  
-   Propiedad <xref:System.Runtime.Serialization.ImportOptions.DataContractSurrogate%2A>. Se puede especificar una implementación <xref:System.Runtime.Serialization.IDataContractSurrogate> con esta propiedad. <xref:System.Runtime.Serialization.IDataContractSurrogate> personaliza el proceso de importación. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Suplentes del contrato de datos](../../../../docs/framework/wcf/extending/data-contract-surrogates.md). De forma predeterminada, no se utiliza ningún suplente.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
 <xref:System.Runtime.Serialization.XsdDataContractImporter>  
 <xref:System.Runtime.Serialization.XsdDataContractExporter>  
 <xref:System.Runtime.Serialization.ImportOptions>  
 [Referencia de esquema de contrato de datos](../../../../docs/framework/wcf/feature-details/data-contract-schema-reference.md)  
 [Suplentes de contratos de datos](../../../../docs/framework/wcf/extending/data-contract-surrogates.md)  
 [Importación y exportación de esquemas](../../../../docs/framework/wcf/feature-details/schema-import-and-export.md)  
 [Exportación de esquemas desde las clases](../../../../docs/framework/wcf/feature-details/exporting-schemas-from-classes.md)  
 [Referencia de esquema de contrato de datos](../../../../docs/framework/wcf/feature-details/data-contract-schema-reference.md)
