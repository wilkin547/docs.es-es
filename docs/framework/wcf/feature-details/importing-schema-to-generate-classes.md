---
title: "Importaci&#243;n del esquema para generar clases | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "WCF, importación y exportación de esquemas"
  - "Clase XsdDataContractImporter"
ms.assetid: b9170583-8c34-43bd-97bb-6c0c8dddeee0
caps.latest.revision: 15
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 15
---
# Importaci&#243;n del esquema para generar clases
Para generar clases a partir de esquemas que se pueden utilizables con [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], utilice el <xref:System.Runtime.Serialization.XsdDataContractImporter> clase. En este tema se describen el proceso y variaciones.  
  
## <a name="the-import-process"></a>El proceso de importación  
 Inicia el proceso de importación de esquema con un <xref:System.Xml.Schema.XmlSchemaSet> y genera un <xref:System.CodeDom.CodeCompileUnit>.  
  
 `XmlSchemaSet` forma parte del Modelo de objetos de esquemas (SOM) de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] que representa un conjunto de documentos de esquema (XSD) de lenguaje de definición de esquemas XML. Para crear un `XmlSchemaSet` de objeto de un conjunto de documentos XSD, deserialice cada documento en un <xref:System.Xml.Schema.XmlSchema> objeto (utilizando el <xref:System.Xml.Serialization.XmlSerializer>) y agregar estos objetos a una nueva `XmlSchemaSet`.  
  
 `CodeCompileUnit` forma parte del Modelo de objetos de documento (CodeDOM) de Código de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] que representa el código [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] de una manera abstracta. Para generar el código real de un `CodeCompileUnit`, utilice una subclase de la <xref:System.CodeDom.Compiler.CodeDomProvider> de clase, como el <xref:Microsoft.CSharp.CSharpCodeProvider> o <xref:Microsoft.VisualBasic.VBCodeProvider> clase.  
  
#### <a name="to-import-a-schema"></a>Importar un esquema  
  
1.  Cree una instancia de la <xref:System.Runtime.Serialization.XsdDataContractImporter>.  
  
2.  Opcional. Pase `CodeCompileUnit` en el constructor. Los tipos generados durante la importación del esquema se agregan a la instancia `CodeCompileUnit` en lugar de iniciarse con un `CodeCompileUnit`en blanco.  
  
3.  Opcional. Llame a uno de los <xref:System.Runtime.Serialization.XsdDataContractImporter.CanImport%2A> métodos. El método determina si el esquema determinado es un esquema de contrato de datos válido y si se puede importar. El método `CanImport` tiene las mismas sobrecargas que `Import` (el paso siguiente).  
  
4.  Llame a uno de los sobrecargados `Import` métodos, por ejemplo, el <xref:System.Runtime.Serialization.XsdDataContractImporter.Import%28System.Xml.Schema.XmlSchemaSet%29> método.  
  
     La sobrecarga más simple toma `XmlSchemaSet` e importa todos los tipos, incluidos los tipos anónimos, situados en ese esquema establecido. Otras sobrecargas permiten especificar el tipo XSD o una lista de tipos a importar (en forma de un <xref:System.Xml.XmlQualifiedName> o una colección de `XmlQualifiedName` objetos). En este caso, solo se importan los tipos especificados. Una sobrecarga toma un <xref:System.Xml.Schema.XmlSchemaElement> que importa un elemento determinado de la `XmlSchemaSet`, así como su tipo asociado (si es anónimo o no). Esta sobrecarga devuelve `XmlQualifiedName`, que representa el nombre de contrato de datos del tipo generado para este elemento.  
  
     Varias llamadas del método `Import` producen como resultado varios elementos que se agregan al mismo `CodeCompileUnit`. Un tipo no se genera en `CodeCompileUnit` si ya existe en este. Llame varias veces `Import` al mismo `XsdDataContractImporter` en lugar de utilizar varios objetos `XsdDataContractImporter`. Ésta es la manera recomendada de evitar que se generen tipos duplicados.  
  
    > [!NOTE]
    >  Si se produce un error durante la importación, `CodeCompileUnit` estará en un estado imprevisible. Si utiliza `CodeCompileUnit` como resultado de una importación en la que se ha producido un error, podría exponerse a vulnerabilidades de seguridad.  
  
5.  Acceso a la `CodeCompileUnit` a través de la <xref:System.Runtime.Serialization.XsdDataContractImporter.CodeCompileUnit%2A> propiedad.  
  
### <a name="import-options-customizing-the-generated-types"></a>Importar opciones: Personalizar los tipos generados  
 Puede establecer la <xref:System.Runtime.Serialization.XsdDataContractImporter.Options%2A> propiedad de la <xref:System.Runtime.Serialization.XsdDataContractImporter> a una instancia de la <xref:System.Runtime.Serialization.ImportOptions> clase para controlar diversos aspectos del proceso de importación. Hay varias opciones influyen directamente en los tipos generados.  
  
#### <a name="controlling-the-access-level-generateinternal-or-the-internal-switch"></a>Controlar el nivel de acceso (GenerateInternal o el modificador /interno)  
 Esto corresponde a la **/ interno** activar la [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).  
  
 Normalmente, los tipos públicos se generan a partir del esquema, con campos privados y propiedades de miembro de datos públicos coincidentes. Para generar tipos internos en su lugar, establezca el <xref:System.Runtime.Serialization.ImportOptions.GenerateInternal%2A> propiedad `true`.  
  
 En el ejemplo siguiente se muestra un esquema transformado en interna clase cuando la <xref:System.Runtime.Serialization.ImportOptions.GenerateInternal%2A> propiedad está establecida en`true.`  
  
 [!code-csharp[c_SchemaImportExport#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/cs/source.cs#2)]
 [!code-vb[c_SchemaImportExport#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_schemaimportexport/vb/source.vb#2)]  
  
#### <a name="controlling-namespaces-namespaces-or-the-namespace-switch"></a>Controlar espacios de nombres (Espacios de nombres o el modificador /espacio de nombres)  
 Esto corresponde a la **/Namespace** activar el `Svcutil.exe` herramienta.  
  
 Normalmente, se generan los tipos generados a partir del esquema en [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] espacios de nombres, con cada espacio de nombres XSD correspondiente a una determinada [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] según una asignación descrita en el espacio de nombres [referencia de esquema de contrato de datos](../../../../docs/framework/wcf/feature-details/data-contract-schema-reference.md). Puede personalizar esta asignación mediante el <xref:System.Runtime.Serialization.ImportOptions.Namespaces%2A> propiedad a un <xref:System.Collections.Generic.Dictionary%602>.\</TKey, TValue> Si se encuentra un espacio de nombres XSD determinado en el diccionario, el espacio de nombres [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] correspondiente también se toma de su diccionario.  
  
 Por ejemplo, considere el siguiente esquema:  
  
 [!code[c_SchemaImportExport#10](../../../../samples/snippets/common/VS_Snippets_CFX/c_schemaimportexport/common/source.config#10)]  
  
 El ejemplo siguiente utiliza la propiedad `Namespaces` para asignar el espacio de nombres "http://schemas.contoso.com/carSchema" a "Contoso.Cars."  
  
 [!code-csharp[c_SchemaImportExport#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/cs/source.cs#8)]
 [!code-vb[c_SchemaImportExport#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_schemaimportexport/vb/source.vb#8)]  
  
#### <a name="adding-the-serializableattribute-generateserializable-or-the-serializable-switch"></a>Agregar SerializableAttribute (GenerateSerializable o el modificador /serializable)  
 Esto corresponde a la **/ serializable** activar el `Svcutil.exe` herramienta.  
  
 A veces es importante para los tipos generados a partir del esquema se puedan utilizar con [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] motores de serialización en tiempo de ejecución (por ejemplo, el <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=fullName> y <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter> clases). Esto es útil cuando se utilizan los tipos para la comunicación remota [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]. Para habilitar esta opción, debe aplicar el <xref:System.SerializableAttribute> de atributo para los tipos generados además regular <xref:System.Runtime.Serialization.DataContractAttribute> atributo. Se genera el atributo automáticamente si la opción de importación `GenerateSerializable` está establecida en `true`.  
  
 El ejemplo siguiente muestra la clase `Vehicle` generada con la opción establecida de importación `GenerateSerializable` a `true`.  
  
 [!code-csharp[c_SchemaImportExport#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/cs/source.cs#4)]
 [!code-vb[c_SchemaImportExport#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_schemaimportexport/vb/source.vb#4)]  
  
#### <a name="adding-data-binding-support-enabledatabinding-or-the-enabledatabinding-switch"></a>Agregar compatibilidad de enlace de datos (EnableDataBinding o el modificador /enableDataBinding)  
 Esto corresponde a la **/enableDataBinding** activar la herramienta Svcutil.exe.  
  
 Es posible que quiera enlazar los tipos generados a partir del esquema a los componentes de interfaz gráfica de usuario para que las actualizaciones en las instancias de estos tipos se actualicen automáticamente en la Interfaz de usuario. El `XsdDataContractImporter` puede generar tipos que implementan la <xref:System.ComponentModel.INotifyPropertyChanged> interfaz de tal forma que cualquier cambio de propiedad desencadena un evento. Si está generando tipos para su uso con un entorno de programación de la interfaz de usuario de cliente que admite esta interfaz (como [!INCLUDE[avalon1](../../../../includes/avalon1-md.md)]), establezca la <xref:System.Runtime.Serialization.ImportOptions.EnableDataBinding%2A> propiedad `true` para habilitar esta característica.  
  
 El ejemplo siguiente se muestra la `Vehicle` clase generada con el <xref:System.Runtime.Serialization.ImportOptions.EnableDataBinding%2A> establecido en `true`.  
  
 [!code-csharp[C_SchemaImportExport#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/cs/source.cs#5)]
 [!code-vb[C_SchemaImportExport#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_schemaimportexport/vb/source.vb#5)]  
  
### <a name="import-options-choosing-collection-types"></a>Opciones de importación: Elegir tipos de colección  
 Dos patrones especiales en XML representan colecciones de elementos: listas de elementos y asociaciones entre un elemento y otro. A continuación se muestra un ejemplo de una lista de cadenas:  
  
 [!code[C_SchemaImportExport#11](../../../../samples/snippets/common/VS_Snippets_CFX/c_schemaimportexport/common/source.config#11)]  
  
 A continuación, se muestra un ejemplo de una asociación entre una cadena y un entero (`city name` y `population`).  
  
 [!code[C_SchemaImportExport#12](../../../../samples/snippets/common/VS_Snippets_CFX/c_schemaimportexport/common/source.config#12)]  
  
> [!NOTE]
>  Las asociaciones también se podrían considerar una lista. Por ejemplo, puede ver la asociación anterior como una lista de objetos `city` complejos que tienen dos campos (un campo de cadena y un campo de valor entero). Ambos patrones tienen una representación en el Esquema XSD. No hay ningún modo de diferenciar entre una lista y una asociación, así que estos patrones siempre se tratan como listas a menos que haya una anotación especial en el esquema específica para [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. La anotación indica que un patrón determinado representa una asociación. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Referencia del esquema de contrato de datos](../../../../docs/framework/wcf/feature-details/data-contract-schema-reference.md).  
  
 Normalmente, una lista se importa como un contrato de datos de colección derivado de una Lista Genérica o como una matriz [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], según si el esquema sigue el patrón estándar de denominación o no para las colecciones. Esto se describe con más detalle en [tipos de colección de contratos de datos](../../../../docs/framework/wcf/feature-details/collection-types-in-data-contracts.md). Las asociaciones se importan normalmente como un <xref:System.Collections.Generic.Dictionary%602> o un contrato de datos de colección que se deriva el objeto de diccionario.\</TKey, TValue> Por ejemplo, considere el siguiente esquema:  
  
 [!code[c_SchemaImportExport#13](../../../../samples/snippets/common/VS_Snippets_CFX/c_schemaimportexport/common/source.config#13)]  
  
 Esto se importaría como se indica a continuación (se muestran los campos en lugar de las propiedades para facilitar la lectura).  
  
 [!code-csharp[c_SchemaImportExport#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/cs/source.cs#6)]
 [!code-vb[c_SchemaImportExport#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_schemaimportexport/vb/source.vb#6)]  
  
 Se pueden personalizar los tipos de colección generados para estos patrones del esquema. Por ejemplo, puede generar colecciones derivadas de la <xref:System.ComponentModel.BindingList%601> en lugar de la <xref:System.Collections.Generic.List%601> clase para enlazar el tipo a un cuadro de lista y que se actualizan automáticamente cuando cambia el contenido de la colección. Para ello, establezca la <xref:System.Runtime.Serialization.ImportOptions.ReferencedCollectionTypes%2A> propiedad de la <xref:System.Runtime.Serialization.ImportOptions> clase a una lista de tipos de colección que se utilizarán (en adelante conocidos como tipos de referencia). Cuando se importa una colección, se digitaliza esta lista de tipos de colección con referencia y, si se encuentra uno, se utiliza la colección que mejor coincida. Las asociaciones solamente se comparan con los tipos que implementan la interfaz genérica o la no genérica <xref:System.Collections.IDictionary> interfaz mientras listas se confrontan con cualquier tipo de colección compatible.  
  
 Por ejemplo, si la <xref:System.Runtime.Serialization.ImportOptions.ReferencedCollectionTypes%2A> propiedad se establece en un <xref:System.ComponentModel.BindingList%601>, el `people` tipo en el ejemplo anterior se genera como sigue.  
  
 [!code-csharp[C_SchemaImportExport#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_schemaimportexport/cs/source.cs#7)]
 [!code-vb[C_SchemaImportExport#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_schemaimportexport/vb/source.vb#7)]  
  
 Se considera que un tipo genérico cerrado es el que más coincide. Por ejemplo, si los tipos de `BindingList(Of Integer)` y <xref:System.Collections.ArrayList> se pasan a la colección de tipos de referencia, se importan las listas de enteros encontradas en el esquema como un `BindingList(Of Integer)`. Cualquier otra lista, por ejemplo, `List(Of String)`, se importa como `ArrayList`.  
  
 Si un tipo que implementa la interfaz `IDictionary` genérica se agrega a la colección de tipos con referencia, sus parámetros de tipo deben estar o totalmente abiertos o totalmente cerrados.  
  
 No se permiten duplicados. Por ejemplo, no puede agregar `List(Of Integer)` sino `Collection(Of Integer)` a los tipos con referencia. Eso haría imposible determinar cuál se debería utilizar cuando una lista de enteros se encuentra en esquema. Los duplicados se detectarán solo si hay un tipo en esquema que expone el problema de los duplicados. Por ejemplo, si el esquema importado no contiene listas de enteros, puede tener `List(Of Integer)` y `Collection(Of Integer)` en la colección de tipos con referencia, pero no tendrán ningún efecto.  
  
 El mecanismo de tipos de colección con referencia funciona igual de bien para las colecciones de tipos complejos (incluso las colecciones de otras colecciones) y no solo para las colecciones de primitivos.  
  
 El `ReferencedCollectionTypes` propiedad se corresponde con el **/collectionType** activar la herramienta SvcUtil.exe. Tenga en cuenta que para hacer referencia a varios tipos de colección, el **/collectionType** conmutador debe especificarse varias veces. Si el tipo no está en MsCorLib.dll, el ensamblado debe también hacer referencia mediante la **/reference** cambiar.  
  
#### <a name="import-options-referencing-existing-types"></a>Opciones de importación: Hacer referencia a tipos existentes  
 De vez en cuando, los tipos en esquema corresponden a los tipos [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] existentes y no es necesario generar estos tipos desde el principio. (Esta sección solo se aplica a los tipos noncollection. Para los tipos de colección, consulte la sección anterior.)  
  
 Por ejemplo, puede tener un tipo de contrato de datos "Persona" estándar para toda la compañía que siempre quiere utilizar cuando represente una persona. Cuando algún servicio utiliza este tipo y su esquema aparece en los metadatos del servicio, puede reutilizar el tipo `Person` existente cuando importe este esquema en lugar de generar uno nuevo para cada servicio.  
  
 Para ello, pase una lista de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] tipos que desee reutilizar en la colección el <xref:System.Runtime.Serialization.ImportOptions.ReferencedTypes%2A> propiedad se devuelve en el <xref:System.Runtime.Serialization.ImportOptions> clase. Si alguno de estos tipos tiene un nombre de contrato de datos y espacio de nombres que coincide con el nombre y espacio de nombres de un tipo de esquema, se realiza una comparación estructural. Si se determina que los tipos coinciden en nombres y en estructuras, el tipo [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] existente se reutiliza en lugar de generar uno nuevo. Si solo coincide el nombre y no la estructura, se produce una excepción. Tenga en cuenta que no hay ninguna concesión para controlar las versiones al hacer referencia a tipos (por ejemplo, agregar nuevos miembros de datos opcionales). Las estructuras deben coincidir con exactitud.  
  
 Es legal agregar varios tipos con el mismo nombre de contrato de datos y espacio de nombres a la colección de tipos con referencia, siempre que no se importe ningún tipo de esquema con ese nombre y espacio de nombres. Esto le permite agregar con facilidad todos los tipos en un ensamblado a la colección sin preocuparse por los duplicados para los tipos que realmente no se producen en esquema.  
  
 El `ReferencedTypes` propiedad se corresponde con el **/reference** conmutador en determinados modos de funcionamiento de la herramienta Svcutil.exe.  
  
> [!NOTE]
>  Cuando se utiliza Svcutil.exe o (en [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]) la **Add Service Reference** herramientas, todos los tipos en MsCorLib.dll automáticamente se hace referencia.  
  
#### <a name="import-options-importing-non-datacontract-schema-as-ixmlserializable-types"></a>Opciones de importación: Importar esquema Non-DataContract como tipos IXmlSerializable  
 El <xref:System.Runtime.Serialization.XsdDataContractImporter> admite un subconjunto limitado del esquema. Si las construcciones de esquema no compatibles están presentes (por ejemplo, atributos XML), se produce un error en los intentos de importación y se genera una excepción. Sin embargo, establecer el <xref:System.Runtime.Serialization.ImportOptions.ImportXmlType%2A> propiedad `true` extiende el intervalo de esquema compatible. Cuando se establece en `true`, <xref:System.Runtime.Serialization.XsdDataContractImporter> genera tipos que implementan la <xref:System.Xml.Serialization.IXmlSerializable> interfaz. Esto permite el acceso directo a la representación XML de estos tipos.  
  
##### <a name="design-considerations"></a>Consideraciones de diseño  
  
-   Puede ser difícil trabajar directamente con la representación XML con tipos débiles. Considere la posibilidad de utilizar un motor de serialización alternativo, como el <xref:System.Xml.Serialization.XmlSerializer>, para trabajar con el esquema no es compatible con datos de contratos en forma fuertemente tipada. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Mediante la clase XmlSerializer](../../../../docs/framework/wcf/feature-details/using-the-xmlserializer-class.md).  
  
-   No se puede importar algunas construcciones de esquema mediante el <xref:System.Runtime.Serialization.XsdDataContractImporter> incluso cuando el <xref:System.Runtime.Serialization.ImportOptions.ImportXmlType%2A> propiedad está establecida en `true`. De nuevo, considere el uso de la <xref:System.Xml.Serialization.XmlSerializer> para estos casos.  
  
-   Las construcciones de esquema exacto que son compatibles cuando <xref:System.Runtime.Serialization.ImportOptions.ImportXmlType%2A> es `true` o `false` se describen en [referencia de esquema de contrato de datos](../../../../docs/framework/wcf/feature-details/data-contract-schema-reference.md).  
  
-   Genera el esquema para <xref:System.Xml.Serialization.IXmlSerializable> tipos no retienen la fidelidad cuando se importan y exportan. Es decir, exportar el esquema a partir de los tipos generados e importar como clases no devuelve el esquema original.  
  
 Es posible combinar la <xref:System.Runtime.Serialization.ImportOptions.ImportXmlType%2A> opción con la <xref:System.ServiceModel.Description.ServiceContractGenerator.ReferencedTypes%2A> opción descrito anteriormente. Para tipos que tienen que ser generados como <xref:System.Xml.Serialization.IXmlSerializable> implementaciones, la comprobación estructural se omite cuando se utiliza la <xref:System.ServiceModel.Description.ServiceContractGenerator.ReferencedTypes%2A> característica.  
  
 El <xref:System.Runtime.Serialization.ImportOptions.ImportXmlType%2A> opción corresponde a la **/importXmlTypes** activar la herramienta Svcutil.exe.  
  
##### <a name="working-with-generated-ixmlserializable-types"></a>Trabajar con tipos generados IXmlSerializable  
 Generado `IXmlSerializable` tipos contienen un campo privado, denominado "nodesField", que devuelve una matriz de <xref:System.Xml.XmlNode> objetos. Cuando se deserializa una instancia de este tipo, usted puede tener acceso directamente a los datos XML a través de este campo utilizando el Modelo de objetos del documento XML. Cuando se serializa una instancia de este tipo, usted puede establecer este campo a los datos XML deseados y se serializará.  
  
 Esto se logra a través de la implementación `IXmlSerializable`. En el archivo `IXmlSerializable` tipo, el <xref:System.Xml.Serialization.IXmlSerializable.ReadXml%2A> implementación llama el <xref:System.Runtime.Serialization.XmlSerializableServices.ReadNodes%2A> método de la <xref:System.Runtime.Serialization.XmlSerializableServices> clase. El método es un método auxiliar que convierte XML proporcionado a través de un <xref:System.Xml.XmlReader> a una matriz de <xref:System.Xml.XmlNode> objetos. El <xref:System.Xml.Serialization.IXmlSerializable.WriteXml%2A> implementación hace lo contrario y convierte la matriz de `XmlNode` objetos en una secuencia de <xref:System.Xml.XmlWriter> llamadas. Esto se logra mediante la <xref:System.Runtime.Serialization.XmlSerializableServices.WriteNodes%2A> método.  
  
 Se puede ejecutar el proceso de exportación del esquema en las clases `IXmlSerializable` generadas. Como se ha expresado previamente, no se le devolverá el esquema original. En su lugar, obtendrá el tipo XSD estándar “anyType”, que es un carácter comodín para cualquier tipo XSD.  
  
 Esto se logra aplicando el <xref:System.Xml.Serialization.XmlSchemaProviderAttribute> atributo generado `IXmlSerializable` clases y especificando un método que llama el <xref:System.Runtime.Serialization.XmlSerializableServices.AddDefaultSchema%2A> método para generar el tipo "anyType".  
  
> [!NOTE]
>  El <xref:System.Runtime.Serialization.XmlSerializableServices> tipo existe solamente para admitir esta característica en particular. No se recomienda utilizarlo para cualquier otro propósito.  
  
#### <a name="import-options-advanced-options"></a>Opciones de importación: Opciones avanzadas  
 Estas son opciones de importación avanzadas:  
  
-   <xref:System.Runtime.Serialization.ImportOptions.CodeProvider%2A> propiedad. Especifique el <xref:System.CodeDom.Compiler.CodeDomProvider> utilizada para generar el código para las clases generadas. El mecanismo de importación intenta evitar características que el <xref:System.CodeDom.Compiler.CodeDomProvider> no admite. Por ejemplo, el lenguaje J# no admite genéricos. Si especifica el proveedor de código de J# en esta propiedad, no se genera ningún tipo genérico en el importador <xref:System.CodeDom.CodeCompileUnit>. Si el <xref:System.Runtime.Serialization.ImportOptions.CodeProvider%2A> no se establece, el conjunto completo de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] características se utiliza sin restricciones.  
  
-   <xref:System.Runtime.Serialization.ImportOptions.DataContractSurrogate%2A> propiedad. Un <xref:System.Runtime.Serialization.IDataContractSurrogate> se puede especificar la implementación con esta propiedad. El <xref:System.Runtime.Serialization.IDataContractSurrogate> personaliza el proceso de importación. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Suplentes de contratos de datos](../../../../docs/framework/wcf/extending/data-contract-surrogates.md). De forma predeterminada, no se utiliza ningún suplente.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Runtime.Serialization.DataContractSerializer>   
 <xref:System.Runtime.Serialization.XsdDataContractImporter>   
 <xref:System.Runtime.Serialization.XsdDataContractExporter>   
 <xref:System.Runtime.Serialization.ImportOptions>   
 [Referencia de esquema de contrato de datos](../../../../docs/framework/wcf/feature-details/data-contract-schema-reference.md)   
 [Suplentes de contratos de datos](../../../../docs/framework/wcf/extending/data-contract-surrogates.md)   
 [Exportación e importación del esquema](../../../../docs/framework/wcf/feature-details/schema-import-and-export.md)   
 [Exportar esquemas a partir de clases](../../../../docs/framework/wcf/feature-details/exporting-schemas-from-classes.md)   
 [Referencia de esquema de contrato de datos](../../../../docs/framework/wcf/feature-details/data-contract-schema-reference.md)