---
description: 'Más información sobre: suplentes de contratos de datos'
title: Suplentes de contratos de datos
ms.date: 03/30/2017
helpviewer_keywords:
- data contracts [WCF], surrogates
ms.assetid: 8c31134c-46c5-4ed7-94af-bab0ac0dfce5
ms.openlocfilehash: 335e7f64868177d00c747e29c463808f3eff3056
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99685808"
---
# <a name="data-contract-surrogates"></a>Suplentes de contratos de datos

El *suplente* del contrato de datos es una característica avanzada que se basa en el modelo del contrato de datos. Esta característica está diseñada para ser utilizada para la personalización de tipo y substitución en situaciones donde los usuarios desean cambiar cómo un tipo se serializa, deserializa o se proyecta en metadatos. Algunos escenarios donde se puede utilizar un suplente es cuando un contrato de datos no se ha especificado para el tipo, los campos y las propiedades no están marcados con el atributo <xref:System.Runtime.Serialization.DataMemberAttribute> o los usuarios desean crear dinámicamente las variaciones del esquema.  
  
 La serialización y deserialización se logran con el suplente del contrato de datos al utilizar <xref:System.Runtime.Serialization.DataContractSerializer> para convertir de .NET Framework en un formato conveniente, como XML. El suplente del contrato de datos también se puede utilizar para modificar los metadatos exportados para los tipos, al generar representaciones de metadatos como documentos de esquema XML (XSD). En la importación, el código se crea a partir de los metadatos y el suplente se puede utilizar en este caso también para personalizar el código generado.  
  
## <a name="how-the-surrogate-works"></a>Cómo funciona el suplente  

 Un suplente funciona asignando un tipo (el tipo "original") a otro tipo (el tipo “suplente”). El ejemplo siguiente muestra el tipo original `Inventory` y un nuevo tipo suplente `InventorySurrogated`. El tipo `Inventory` no se puede serializar pero el tipo `InventorySurrogated` es:  
  
 [!code-csharp[C_IDataContractSurrogate#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_idatacontractsurrogate/cs/source.cs#1)]  
  
 Dado que un contrato de datos no se ha definido para esta clase, convierta la clase en una clase de suplente con un contrato de datos. La clase de suplente se muestra en el ejemplo siguiente:  
  
 [!code-csharp[C_IDataContractSurrogate#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_idatacontractsurrogate/cs/source.cs#2)]  
  
## <a name="implementing-the-idatacontractsurrogate"></a>Implementar IDataContractSurrogate  

 Para utilizar el suplente del contrato de datos, implemente la interfaz <xref:System.Runtime.Serialization.IDataContractSurrogate>.  
  
 A continuación, se muestra una información general de cada método de <xref:System.Runtime.Serialization.IDataContractSurrogate> con una posible implementación.  
  
### <a name="getdatacontracttype"></a>GetDataContractType  

 El método <xref:System.Runtime.Serialization.IDataContractSurrogate.GetDataContractType%2A> asigna un tipo a otro. Este método se requiere para la serialización, deserialización, importación y exportación.  
  
 La primera tarea está definiendo qué tipos se asignarán a otros tipos. Por ejemplo:  
  
 [!code-csharp[C_IDataContractSurrogate#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_idatacontractsurrogate/cs/source.cs#3)]  
  
- Durante la serialización, la asignación devuelta por este método se utiliza subsiguientemente para transformar la instancia original en una instancia suplente llamando al método <xref:System.Runtime.Serialization.IDataContractSurrogate.GetObjectToSerialize%2A>.  
  
- Durante la deserialización la asignación devuelta por este método es utilizada por el serializador para deserializar en una instancia del tipo suplente. Llama subsiguientemente a <xref:System.Runtime.Serialization.IDataContractSurrogate.GetDeserializedObject%2A> para transformar la instancia suplente en una instancia del tipo original.  
  
- Durante la exportación, el tipo de suplente devuelto por este método se refleja para obtener el contrato de datos para utilizar para generar los metadatos.  
  
- Durante la importación, el tipo inicial se cambia a un tipo suplente que se refleja para obtener el contrato de datos para utilizarlos para propósitos como referenciar el soporte.  
  
 El parámetro <xref:System.Type> es el tipo del objeto que se serializa, deserializa, importa o exporta. El método <xref:System.Runtime.Serialization.IDataContractSurrogate.GetDataContractType%2A> debe devolver el tipo de entrada si el suplente no controla el tipo. De lo contrario, devuelva el tipo suplente adecuado. Si existen varios tipos suplentes, las numerosas asignaciones se pueden definir en este método.  
  
 No se llama al método <xref:System.Runtime.Serialization.IDataContractSurrogate.GetDataContractType%2A> para los tipos primitivos integrados del contrato de datos, como <xref:System.Int32> o <xref:System.String>. Para otros tipos, como matrices, tipos definidos por el usuario y otras estructuras de datos, se llamará a este método para cada tipo.  
  
 En el ejemplo anterior, el método comprueba si el parámetro `type` y `Inventory` son comparables. En tal caso, el método lo asigna a `InventorySurrogated`. Cuando se llama una serialización, deserialización, esquema de importación o esquema de exportación, se llama primero a esta función para determinar la asignación entre los tipos.  
  
### <a name="getobjecttoserialize-method"></a>Método GetObjectToSerialize  

 El método <xref:System.Runtime.Serialization.IDataContractSurrogate.GetObjectToSerialize%2A> convierte la instancia de tipo original en la instancia de tipo suplente. El método se requiere para la serialización.  
  
 El paso siguiente es definir la manera en que los datos físicos se asignarán de la instancia original a la instancia suplente implementando el método <xref:System.Runtime.Serialization.IDataContractSurrogate.GetObjectToSerialize%2A>. Por ejemplo:  
  
 [!code-csharp[C_IDataContractSurrogate#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_idatacontractsurrogate/cs/source.cs#4)]  
  
 Se llama al método <xref:System.Runtime.Serialization.IDataContractSurrogate.GetObjectToSerialize%2A> cuando se serializa un objeto. Este método transfiere los datos del tipo original a los campos del tipo suplente. Los campos pueden estar asignados directamente a campos suplentes o las manipulaciones de los datos originales pueden estar almacenadas en el suplente. Algunos posibles usos incluyen: asignar directamente los campos, realizar operaciones en los datos que se van a almacenar en los campos suplentes o almacenar el XML del tipo original en el campo suplente.  
  
 El parámetro `targetType` hace referencia al tipo declarado del miembro. Este parámetro es el tipo suplente devuelto por el método <xref:System.Runtime.Serialization.IDataContractSurrogate.GetDataContractType%2A>. El serializador no exige que el objeto devuelto se pueda asignar a este tipo. El `obj` parámetro es el objeto que se va a serializar y se convertirá en su suplente si es necesario. Este método debe devolver el objeto de entrada si el suplente no controla el objeto. De lo contrario, se devolverá el nuevo objeto suplente. No se llama al suplente si el objeto es NULL. Las numerosas asignaciones del suplente para las diferentes instancias se pueden definir dentro de este método.  
  
 Al crear <xref:System.Runtime.Serialization.DataContractSerializer>, puede indicarle que conserve las referencias a objeto. (Para obtener más información, vea [serialización y deserialización](../feature-details/serialization-and-deserialization.md)). Esto se hace estableciendo el `preserveObjectReferences` parámetro en su constructor en `true` . En tal caso, se llama al suplente solo una vez para un objeto puesto que todas las serializaciones subsiguientes simplemente escriben la referencia en la secuencia. Si `preserveObjectReferences` está establecido en `false`, se llama al suplente cada vez que se encuentra una instancia.  
  
 Si el tipo de la instancia serializada difiere del tipo declarado, la información de tipo se escribe en la secuencia, por ejemplo, `xsi:type` para permitir deserializar la instancia en el otro extremo. Este proceso se produce tanto si el objeto es suplente como si no.  
  
 El ejemplo anterior convierte los datos de la instancia `Inventory` en `InventorySurrogated`. Comprueba el tipo del objeto y realiza las manipulaciones necesarias para convertirlo al tipo suplente. En este caso, los campos de la clase `Inventory` se copian directamente encima de los campos de la clase `InventorySurrogated`.  
  
### <a name="getdeserializedobject-method"></a>Método GetDeserializedObject  

 El método <xref:System.Runtime.Serialization.IDataContractSurrogate.GetDeserializedObject%2A> convierte la instancia de tipo suplente en la instancia de tipo original. Se requiere para la deserialización.  
  
 La tarea siguiente es definir la manera en que los datos físicos se asignarán de la instancia suplente a la instancia original. Por ejemplo:  
  
 [!code-csharp[C_IDataContractSurrogate#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_idatacontractsurrogate/cs/source.cs#5)]  
  
 Se llama a este método solo durante la deserialización de un objeto. Proporciona asignación inversa de datos para la deserialización del tipo suplente a su tipo original. Similar al método `GetObjectToSerialize`, algunos posibles usos pueden ser intercambiar directamente los datos de campo, realizar las operaciones en los datos y almacenar los datos XML. Al deserializar, no siempre obtendrá los valores de datos exactos del original debido a las manipulaciones en la conversión de datos.  
  
 El parámetro `targetType` hace referencia al tipo declarado del miembro. Este parámetro es el tipo suplente devuelto por el método `GetDataContractType`. El `obj` parámetro hace referencia al objeto que se ha deserializado. El objeto se puede convertir de nuevo en su tipo original si es suplente. Este método devuelve el objeto de entrada si el suplente no controla el objeto. De lo contrario, se devolverá el objeto deserializado una vez se haya completado su conversión. Si existen varios tipos de suplente, puede proporcionar la conversión de datos del suplente al tipo primario para cada uno indicando cada tipo y su conversión.  
  
 Al devolver un objeto, las tablas de objeto internas se actualizan con el objeto devuelto por este suplente. Cualquier referencia subsiguiente a una instancia obtendrá la instancia suplente de las tablas de objeto.  
  
 El ejemplo anterior vuelve a convertir objetos de tipo `InventorySurrogated` en el tipo `Inventory`inicial. En este caso, los datos se transfieren directamente desde `InventorySurrogated` a sus campos correspondiendo en `Inventory`. Puesto que no hay manipulaciones de datos, el cada uno de los campos de miembro contendrá los mismos valores como antes de la serialización.  
  
### <a name="getcustomdatatoexport-method"></a>Método GetCustomDataToExport  

 Al exportar un esquema, el método <xref:System.Runtime.Serialization.IDataContractSurrogate.GetCustomDataToExport%2A> es opcional. Se utiliza para insertar datos adicionales o sugerencias en el esquema exportado. Los datos adicionales se pueden insertar en el nivel de miembro o el nivel de tipo. Por ejemplo:  
  
 [!code-csharp[C_IDataContractSurrogate#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_idatacontractsurrogate/cs/source.cs#6)]  
  
 Este método (con dos sobrecargas) habilita la inclusión de información adicional en los metadatos en el nivel de miembro o en el nivel de tipo. Es posible incluir sugerencias sobre si un miembro es público o privado, y comentarios que se conservarían a lo largo de la exportación e importación del esquema. Tal información se perdería sin este método. Este método no provoca la inserción o eliminación de miembros o tipos, sino que agrega datos adicionales a los esquemas en cualquiera de estos niveles.  
  
 El método está sobrecargado y puede tomar `Type` (parámetro `clrtype`) o <xref:System.Reflection.MemberInfo> (parámetro `memberInfo`). El segundo parámetro es siempre `Type` (parámetro `dataContractType`). Se llama a este método para cada miembro y tipo del tipo suplente `dataContractType`.  
  
 Cualquiera de estas sobrecargas debe devolver `null` o un objeto serializable. Un objeto no NULL se serializará como anotación en el esquema exportado. Para la sobrecarga `Type`, cada tipo que se exporta al esquema se envía a este método en el primer parámetro junto con el tipo suplente como el parámetro `dataContractType`. Para la sobrecarga `MemberInfo`, cada miembro que se exporta al esquema envía su información como el parámetro `memberInfo` con el tipo suplente en el segundo parámetro.  
  
#### <a name="getcustomdatatoexport-method-type-type"></a>Método GetCustomDataToExport (Tipo, Tipo)  

 Se llama al método <xref:System.Runtime.Serialization.IDataContractSurrogate.GetCustomDataToExport%28System.Type%2CSystem.Type%29?displayProperty=nameWithType> durante la exportación de esquema para cada definición de tipo. El método agrega información a los tipos dentro del esquema al exportar. Cada tipo definido se envía a este método para determinar si hay datos adicionales que deban incluirse en el esquema.  
  
#### <a name="getcustomdatatoexport-method-memberinfo-type"></a>Método GetCustomDataToExport (MemberInfo, Tipo)  

 Se llama a <xref:System.Runtime.Serialization.IDataContractSurrogate.GetCustomDataToExport%28System.Reflection.MemberInfo%2CSystem.Type%29?displayProperty=nameWithType> durante la exportación para cada miembro en los tipos que se exportan. Esta función le permite personalizar cualquier comentario para los miembros que se incluirán en el esquema durante la exportación. La información para cada miembro dentro de la clase se envía a este método para comprobar si deben agregarse datos adicionales en el esquema.  
  
 El ejemplo anterior realiza búsquedas a través de `dataContractType` para cada miembro del suplente. Después devuelve el modificador de acceso adecuado para cada campo. Sin esta personalización, el valor predeterminado para los modificadores de acceso es público. Por consiguiente, todos los miembros se definirían como públicos en el código generado utilizando el esquema exportado sin importar cuáles sean sus restricciones de acceso. Si no se utilizara esta implementación, el miembro `numpens` sería público en el esquema exportado aunque se hubiera definido en el suplente como privado. A través del uso de este método, en el esquema exportado, el modificador de acceso se puede generar como privado.  
  
### <a name="getreferencedtypeonimport-method"></a>Método GetReferencedTypeOnImport  

 Este método asigna <xref:System.Type> del suplente al tipo original. Este método es opcional para la importación del esquema.  
  
 Al crear un suplente que importa un esquema y genera el código para él, la tarea siguiente es definir el tipo de una instancia suplente en relación a su tipo original.  
  
 Si el código generado necesita hacer referencia a un tipo de usuario existente, esto se hace implementando el método <xref:System.Runtime.Serialization.IDataContractSurrogate.GetReferencedTypeOnImport%2A>.  
  
 Al importar un esquema, se llama a este método para cada declaración de tipos para asignar el contrato de datos suplente a un tipo. Los parámetros de cadena `typeName` y `typeNamespace` definen el nombre y espacio de nombres del tipo suplente. El valor devuelto para <xref:System.Runtime.Serialization.IDataContractSurrogate.GetReferencedTypeOnImport%2A> se utiliza para determinar si debe generarse un nuevo tipo. Este método debe devolver un tipo válido o NULL. Para los tipos válidos, el tipo devuelto se utilizará como un tipo referenciado en el código generado. Si se devuelve NULL, no se referenciará ningún tipo y deberá crearse un nuevo tipo. Si existen varios suplentes, es posible volver a realizar la asignación para cada tipo suplente a su tipo inicial.  
  
 El parámetro `customData` es originalmente el objeto devuelto de <xref:System.Runtime.Serialization.IDataContractSurrogate.GetCustomDataToExport%2A>. Se utiliza `customData` cuando los autores suplentes desean insertar datos adicionales/sugerencias en los metadatos para utilizar durante importación para generar código.  
  
### <a name="processimportedtype-method"></a>Método ProcessImportedType  

 El método <xref:System.Runtime.Serialization.IDataContractSurrogate.ProcessImportedType%2A> personaliza cualquier tipo creado a partir de la importación del esquema. Este método es opcional.  
  
 Al importar un esquema, este método permite la personalización de cualquiera tipo importado e información de compilación. Por ejemplo:  
  
 [!code-csharp[C_IDataContractSurrogate#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_idatacontractsurrogate/cs/source.cs#7)]  
  
 Durante la importación, se llama a este método para cada tipo generado. Cambie el <xref:System.CodeDom.CodeTypeDeclaration> especificado o modifique <xref:System.CodeDom.CodeCompileUnit>. Esto incluye cambiar el nombre, miembros, atributos y muchas otras propiedades de `CodeTypeDeclaration`. Al procesar `CodeCompileUnit`, es posible modificar las directivas, espacios de nombres, ensamblados referenciados y varios otros aspectos.  
  
 El parámetro `CodeTypeDeclaration` contiene la declaración de tipos de código DOM. El parámetro `CodeCompileUnit` permite la modificación para procesar el código.  Devolver los resultados `null` descartados en la declaración de tipos. A la inversa, al devolver `CodeTypeDeclaration`, se conservan las modificaciones.  
  
 Si se insertan datos personalizados durante la exportación de metadatos, debe ser proporcionado al usuario durante la importación para que lo pueda utilizar. Estos datos personalizados se pueden utilizar para las sugerencias del modelo de programación u otros comentarios. Cada instancia `CodeTypeDeclaration` y <xref:System.CodeDom.CodeTypeMember> incluye datos personalizados como la propiedad <xref:System.CodeDom.CodeObject.UserData%2A>, convertida al tipo `IDataContractSurrogate`.  
  
 El ejemplo anterior realiza algunos cambios en el esquema importado. El código conserva los miembros privados del tipo original utilizando un suplente. El modificador de acceso predeterminado al importar un esquema es `public`. Por consiguiente, todos los miembros del esquema suplente serán públicos a menos que se hayan modificado, como en este ejemplo. Durante la exportación, los datos personalizados se insertan en los metadatos sobre qué miembros son privados. El ejemplo consulta los datos personalizados, comprueba si el modificador de acceso es privado y, a continuación, modifica el miembro adecuado para que sea privado estableciendo sus atributos. Sin esta personalización, el miembro `numpens` se definiría como público en lugar de privado.  
  
### <a name="getknowncustomdatatypes-method"></a>Método GetKnownCustomDataTypes  

 Este método obtiene tipos de datos personalizados definidos a partir del esquema. Este método es opcional para la importación del esquema.  
  
 Se llama al método al principio de la exportación e importación del esquema. El método devuelve los tipos de datos personalizados utilizados en el esquema exportado o importado. El método se pasa a <xref:System.Collections.ObjectModel.Collection%601> (el parámetro `customDataTypes`), que es una colección de tipos. El método debería agregar los tipos conocidos adicionales a esta colección. Los tipos de datos personalizados conocidos son necesarios para habilitar la serialización y deserialización de datos personalizados utilizando <xref:System.Runtime.Serialization.DataContractSerializer>. Para obtener más información, vea [tipos conocidos de contratos de datos](../feature-details/data-contract-known-types.md).  
  
## <a name="implementing-a-surrogate"></a>Implementar un suplente  

 Para utilizar el suplente del contrato de datos en WCF, debe seguir algunos procedimientos especiales.  
  
### <a name="to-use-a-surrogate-for-serialization-and-deserialization"></a>Para utilizar un suplente para la serialización y deserialización  

 Utilice <xref:System.Runtime.Serialization.DataContractSerializer> para realizar la serialización y deserialización de datos con el suplente. <xref:System.Runtime.Serialization.DataContractSerializer> es creado por <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>. También se debe especificar el suplente.  
  
##### <a name="to-implement-serialization-and-deserialization"></a>Para implementar serialización y deserialización  
  
1. Cree una instancia de <xref:System.ServiceModel.ServiceHost> para su servicio. Para obtener instrucciones completas, vea [programación básica de WCF](../basic-wcf-programming.md).  
  
2. Para cada <xref:System.ServiceModel.Description.ServiceEndpoint> del host del servicio especificado, busque <xref:System.ServiceModel.Description.OperationDescription>.  
  
3. Busque a través de los comportamientos de la operación para determinar si se encuentra una instancia de <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>.  
  
4. Si se encuentra <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>, establezca su propiedad <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior.DataContractSurrogate%2A> en una nueva instancia del suplente. Si no se encuentra <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>, cree una nueva instancia y establezca el miembro <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior.DataContractSurrogate%2A> del nuevo comportamiento en una nueva instancia del suplente.  
  
5. Finalmente, agregue este nuevo comportamiento a los comportamientos actuales de la operación, como se muestra en el ejemplo siguiente:  
  
     [!code-csharp[C_IDataContractSurrogate#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_idatacontractsurrogate/cs/source.cs#8)]  
  
### <a name="to-use-a-surrogate-for-metadata-import"></a>Para utilizar un suplente para importar metadatos  

 Al importar los metadatos como WSDL y XSD para generar el código del lado del cliente, el suplente debe ser agregado al componente responsable para generar código del esquema XSD, <xref:System.Runtime.Serialization.XsdDataContractImporter>. Para ello, directamente modifique <xref:System.ServiceModel.Description.WsdlImporter> utilizado para importar los metadatos.  
  
##### <a name="to-implement-a-surrogate-for-metadata-importation"></a>Para implementar un suplente para la importación de metadatos  
  
1. Importe los metadatos mediante la clase <xref:System.ServiceModel.Description.WsdlImporter>.  
  
2. Utilice el método <xref:System.Collections.Generic.Dictionary%602.TryGetValue%2A> para comprobar si se ha definido <xref:System.Runtime.Serialization.XsdDataContractImporter>.  
  
3. Si el método <xref:System.Collections.Generic.Dictionary%602.TryGetValue%2A> devuelve `false`, cree un nuevo <xref:System.Runtime.Serialization.XsdDataContractImporter> y establece su propiedad <xref:System.Runtime.Serialization.XsdDataContractImporter.Options%2A> a una nueva instancia de la clase <xref:System.Runtime.Serialization.ImportOptions>. De lo contrario, utilice el importador devuelto por el parámetro `out` del método <xref:System.Collections.Generic.Dictionary%602.TryGetValue%2A>.  
  
4. Si <xref:System.Runtime.Serialization.XsdDataContractImporter> no tiene <xref:System.Runtime.Serialization.ImportOptions> definido, establezca la propiedad para que sea una nueva instancia de la clase <xref:System.Runtime.Serialization.ImportOptions>.  
  
5. Establezca la propiedad <xref:System.Runtime.Serialization.ImportOptions.DataContractSurrogate%2A> de <xref:System.Runtime.Serialization.ImportOptions> de <xref:System.Runtime.Serialization.XsdDataContractImporter> en una nueva instancia del suplente.  
  
6. Agregue <xref:System.Runtime.Serialization.XsdDataContractImporter> a la colección devuelta por la propiedad <xref:System.ServiceModel.Description.MetadataExporter.State%2A> de <xref:System.ServiceModel.Description.WsdlImporter> (heredada de la clase <xref:System.ServiceModel.Description.MetadataExporter>).  
  
7. Utilice el método <xref:System.ServiceModel.Description.WsdlImporter.ImportAllContracts%2A> de <xref:System.ServiceModel.Description.WsdlImporter> para importar todos los contratos de datos dentro del esquema. Durante el último paso, el código se genera a partir de los esquemas cargados llamando en el suplente.  
  
     [!code-csharp[C_IDataContractSurrogate#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_idatacontractsurrogate/cs/source.cs#9)]  
  
### <a name="to-use-a-surrogate-for-metadata-export"></a>Para utilizar un suplente para exportar metadatos  

 De forma predeterminada, cuando se exportan metadatos de WCF para un servicio, es necesario generar el esquema de WSDL y XSD. El suplente necesita ser agregado al componente responsable para generar el esquema XSD para los tipos de contrato de datos, <xref:System.Runtime.Serialization.XsdDataContractExporter>. Para ello, utilice un comportamiento que implemente <xref:System.ServiceModel.Description.IWsdlExportExtension> para modificar <xref:System.ServiceModel.Description.WsdlExporter>o directamente modifique <xref:System.ServiceModel.Description.WsdlExporter> utilizado para exportar los metadatos.  
  
##### <a name="to-use-a-surrogate-for-metadata-export"></a>Para utilizar un suplente para exportar metadatos  
  
1. Cree un nuevo <xref:System.ServiceModel.Description.WsdlExporter> o utilice el parámetro `wsdlExporter` pasado al método <xref:System.ServiceModel.Description.IWsdlExportExtension.ExportContract%2A>.  
  
2. Utilice la función <xref:System.Collections.Generic.Dictionary%602.TryGetValue%2A> para comprobar si se ha definido <xref:System.Runtime.Serialization.XsdDataContractExporter>.  
  
3. Si <xref:System.Collections.Generic.Dictionary%602.TryGetValue%2A> devuelve `false`, cree un nuevo <xref:System.Runtime.Serialization.XsdDataContractExporter> con los esquemas XML generados de <xref:System.ServiceModel.Description.WsdlExporter>y agréguelo a la colección devuelta por la propiedad <xref:System.ServiceModel.Description.MetadataExporter.State%2A> de <xref:System.ServiceModel.Description.WsdlExporter>. De lo contrario, utilice el exportador devuelto por el parámetro `out` del método <xref:System.Collections.Generic.Dictionary%602.TryGetValue%2A>.  
  
4. Si <xref:System.Runtime.Serialization.XsdDataContractExporter> no tiene <xref:System.Runtime.Serialization.ExportOptions> definido, establezca la propiedad <xref:System.Runtime.Serialization.XsdDataContractExporter.Options%2A> en una nueva instancia de la clase <xref:System.Runtime.Serialization.ExportOptions>.  
  
5. Establezca la propiedad <xref:System.Runtime.Serialization.ExportOptions.DataContractSurrogate%2A> de <xref:System.Runtime.Serialization.ExportOptions> de <xref:System.Runtime.Serialization.XsdDataContractExporter> en una nueva instancia del suplente. Los pasos subsiguientes para exportar los metadatos no requieren ningún cambio.  
  
     [!code-csharp[C_IDataContractSurrogate#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_idatacontractsurrogate/cs/source.cs#10)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.Runtime.Serialization.IDataContractSurrogate>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- <xref:System.Runtime.Serialization.ImportOptions>
- <xref:System.Runtime.Serialization.ExportOptions>
- [Utilización de contratos de datos](../feature-details/using-data-contracts.md)
