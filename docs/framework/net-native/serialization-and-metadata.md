---
title: "Serializaci&#243;n y metadatos | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 619ecf1c-1ca5-4d66-8934-62fe7aad78c6
caps.latest.revision: 7
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 7
---
# Serializaci&#243;n y metadatos
Si la aplicación serializa y deserializa objetos, es posible que deba agregar entradas al archivo de directivas en tiempo de ejecución \(.rd.xml\) para asegurarse de que los metadatos necesarios están presentes en tiempo de ejecución.  Existen dos categorías de serializadores y cada una requiere un tratamiento distinto en el archivo de directivas en tiempo de ejecución:  
  
-   Serializadores de terceros basados en la reflexión.  Estos requieren modificaciones en el archivo de directivas en tiempo de ejecución y se describen en la sección siguiente.  
  
-   Serializadores no basados en reflexión que se encuentran en la biblioteca de clases de. NET Framework.  Estos pueden requerir modificaciones en el archivo de directivas en tiempo de ejecución y se explican en la sección [Serializadores de Microsoft](#Microsoft).  
  
<a name="ThirdParty"></a>   
## Serializadores de terceros  
 Los serializadores de terceros, entre los que está Newtonsoft.JSON, normalmente están basados en reflexión.  Dado un objeto binario grande \(BLOB\) de datos serializados, los campos de los datos se asignan a un tipo concreto mediante la búsqueda por nombre de los campos del tipo de destino.  Como mínimo, el uso de estas bibliotecas produce excepciones [MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md) para cada objeto <xref:System.Type> que se intenta serializar o deserializar en una colección `List<Type>`.  
  
 La forma más sencilla de solucionar los problemas causados por la falta de metadatos para estos serializadores es recopilar los tipos que se utilizarán en la serialización en un único espacio de nombres \(como `App.Models`\) y aplicar una directiva de metadatos `Serialize`:  
  
```  
<Namespace Name="App.Models" Serialize="Required PublicAndInternal" />  
```  
  
 Para obtener información acerca de la sintaxis utilizada en el ejemplo, consulte [Elemento \<Namespace\>](../../../docs/framework/net-native/namespace-element-net-native.md).  
  
<a name="Microsoft"></a>   
## Serializadores de Microsoft  
 Aunque las clases <xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> y <xref:System.Xml.Serialization.XmlSerializer> no se basan en la reflexión, necesitan generar código en función del objeto que se va a serializar o deserializar.  Los constructores sobrecargados de cada serializador incluyen un parámetro <xref:System.Type> que especifica el tipo que se va a serializar o deserializar.  La forma de especificar ese tipo en el código define la acción que se debe realizar, como se explica en las dos secciones siguientes.  
  
### typeof utilizado en el constructor  
 Si llama a un constructor de estas clases de serialización e incluye la palabra clave [typeof](../Topic/typeof%20\(C%23%20Reference\).md) de C\# en la llamada de método, **no tiene que hacer nada más**.  Por ejemplo, en cada una de las siguientes llamadas a un constructor de clase de serialización, la palabra clave `typeof` se utiliza como parte de la expresión que se pasa al constructor.  
  
 [!code-csharp[ProjectN#5](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/serialize1.cs#5)]  
  
 El compilador de [!INCLUDE[net_native](../../../includes/net-native-md.md)] controlará automáticamente este código.  
  
### typeof usado fuera del constructor  
 Si llama a un constructor de estas clases de serialización y utiliza la palabra clave [typeof](../Topic/typeof%20\(C%23%20Reference\).md) de C\# fuera de la expresión proporcionada al parámetro <xref:System.Type> del constructor, como en el código siguiente, el compilador de [!INCLUDE[net_native](../../../includes/net-native-md.md)] no puede resolver el tipo:  
  
 [!code-csharp[ProjectN#6](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/serialize1.cs#6)]  
  
 En este caso, debe especificar el tipo en el archivo de directivas de tiempo de ejecución mediante la adición de una entrada como la siguiente:  
  
```  
<Type Name="DataSet" Browse="Required Public" />  
```  
  
 Del mismo modo, si llama a un constructor como [XmlSerializer.XmlSerializer\(Type, Type\<xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.Type%5B%5D%29?displayProperty=fullName> y proporciona una matriz de objetos <xref:System.Type> adicionales para serializar, como en el código siguiente, el compilador de [!INCLUDE[net_native](../../../includes/net-native-md.md)] no puede resolver estos tipos.  
  
 [!code-csharp[ProjectN#7](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/serialize1.cs#7)]  
  
 Debe agregar entradas como la siguiente para cada tipo en el archivo de directivas de tiempo de ejecución:  
  
```  
<Type Name="t" Browse="Required Public" />  
```  
  
 Para obtener información acerca de la sintaxis utilizada en el ejemplo, consulte [Elemento \<Type\>](../../../docs/framework/net-native/type-element-net-native.md).  
  
## Vea también  
 [Referencia del archivo de configuración de directivas en tiempo de ejecución \(rd.xml\)](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)   
 [Elementos de directivas en tiempo de ejecución](../../../docs/framework/net-native/runtime-directive-elements.md)   
 [Elemento \<Type\>](../../../docs/framework/net-native/type-element-net-native.md)   
 [Elemento \<Namespace\>](../../../docs/framework/net-native/namespace-element-net-native.md)