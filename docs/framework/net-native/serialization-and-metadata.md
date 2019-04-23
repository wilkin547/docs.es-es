---
title: Serialización y metadatos
ms.date: 03/30/2017
ms.assetid: 619ecf1c-1ca5-4d66-8934-62fe7aad78c6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c82d32fe5b1e62a19ff5e2920c5943f1303b2d64
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59207037"
---
# <a name="serialization-and-metadata"></a><span data-ttu-id="73033-102">Serialización y metadatos</span><span class="sxs-lookup"><span data-stu-id="73033-102">Serialization and Metadata</span></span>
<span data-ttu-id="73033-103">Si la aplicación serializa y deserializa objetos, es posible que deba agregar entradas al archivo de directivas en tiempo de ejecución (.rd.xml) para asegurarse de que los metadatos necesarios están presentes en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="73033-103">If your app serializes and deserializes objects, you may need to add entries to your runtime directives (.rd.xml) file to ensure that the necessary metadata is present at run time.</span></span> <span data-ttu-id="73033-104">Existen dos categorías de serializadores y cada una requiere un tratamiento distinto en el archivo de directivas en tiempo de ejecución:</span><span class="sxs-lookup"><span data-stu-id="73033-104">There are two categories of serializers, and each requires different handling in your runtime directives file:</span></span>  
  
-   <span data-ttu-id="73033-105">Serializadores de terceros basados en la reflexión.</span><span class="sxs-lookup"><span data-stu-id="73033-105">Reflection-based third-party serializers.</span></span> <span data-ttu-id="73033-106">Estos requieren modificaciones en el archivo de directivas en tiempo de ejecución y se describen en la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="73033-106">These require modifications to your runtime directives file, and are discussed in the next section.</span></span>  
  
-   <span data-ttu-id="73033-107">Serializadores no basados en reflexión que se encuentran en la biblioteca de clases de. NET Framework.</span><span class="sxs-lookup"><span data-stu-id="73033-107">Non-reflection based serializers found in the .NET Framework class library.</span></span> <span data-ttu-id="73033-108">Estos pueden exigir modificaciones en el archivo de directivas en tiempo de ejecución, y se explican en la sección [Serializadores de Microsoft](#Microsoft).</span><span class="sxs-lookup"><span data-stu-id="73033-108">These may require modifications to your runtime directives file, and are discussed in the [Microsoft serializers](#Microsoft) section.</span></span>  
  
<a name="ThirdParty"></a>   
## <a name="third-party-serializers"></a><span data-ttu-id="73033-109">Serializadores de terceros</span><span class="sxs-lookup"><span data-stu-id="73033-109">Third-party serializers</span></span>  
 <span data-ttu-id="73033-110">Los serializadores de terceros, entre los que está Newtonsoft.JSON, normalmente están basados en reflexión.</span><span class="sxs-lookup"><span data-stu-id="73033-110">Third-part serializers, including Newtonsoft.JSON, typically are reflection-based.</span></span> <span data-ttu-id="73033-111">Dado un objeto binario grande (BLOB) de datos serializados, los campos de los datos se asignan a un tipo concreto mediante la búsqueda por nombre de los campos del tipo de destino.</span><span class="sxs-lookup"><span data-stu-id="73033-111">Given a binary large object (BLOB) of serialized data, the fields in the data are assigned to a concrete type by looking up the fields of the target type by name.</span></span> <span data-ttu-id="73033-112">Como mínimo, el empleo de estas bibliotecas produce excepciones [MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md) para cada objeto <xref:System.Type> que se intenta serializar o deserializar en una colección `List<Type>`.</span><span class="sxs-lookup"><span data-stu-id="73033-112">At a minimum, using these libraries causes [MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md) exceptions for each <xref:System.Type> object that you try to serialize or deserialize in a `List<Type>` collection.</span></span>  
  
 <span data-ttu-id="73033-113">La forma más sencilla de solucionar los problemas causados por la falta de metadatos para estos serializadores es recopilar los tipos que se utilizarán en la serialización en un único espacio de nombres (como `App.Models`) y aplicar una directiva de metadatos `Serialize`:</span><span class="sxs-lookup"><span data-stu-id="73033-113">The easiest way to address issues caused by missing metadata for these serializers is to collect types that will be used in serialization under a single namespace (such as `App.Models`) and apply a `Serialize` metadata directive to it:</span></span>  
  
```xml  
<Namespace Name="App.Models" Serialize="Required PublicAndInternal" />  
```  
  
 <span data-ttu-id="73033-114">Para más información sobre la sintaxis usada en el ejemplo, vea [Elemento \<Namespace>](../../../docs/framework/net-native/namespace-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="73033-114">For information about the syntax used in the example, see [\<Namespace> Element](../../../docs/framework/net-native/namespace-element-net-native.md).</span></span>  
  
<a name="Microsoft"></a>   
## <a name="microsoft-serializers"></a><span data-ttu-id="73033-115">Serializadores de Microsoft</span><span class="sxs-lookup"><span data-stu-id="73033-115">Microsoft serializers</span></span>  
 <span data-ttu-id="73033-116">Aunque las clases <xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> y <xref:System.Xml.Serialization.XmlSerializer> no se basan en la reflexión, necesitan generar código en función del objeto que se va a serializar o deserializar.</span><span class="sxs-lookup"><span data-stu-id="73033-116">Although the <xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>, and <xref:System.Xml.Serialization.XmlSerializer> classes do not rely on reflection, they do require code to be generated based on the object to be serialized or deserialized.</span></span> <span data-ttu-id="73033-117">Los constructores sobrecargados de cada serializador incluyen un parámetro <xref:System.Type> que especifica el tipo que se va a serializar o deserializar.</span><span class="sxs-lookup"><span data-stu-id="73033-117">The overloaded constructors for each serializer include a <xref:System.Type> parameter that specifies the type to be serialized or deserialized.</span></span> <span data-ttu-id="73033-118">La forma de especificar ese tipo en el código define la acción que se debe realizar, como se explica en las dos secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="73033-118">How you specify that type in your code defines the action you must take, as discussed in the next two sections.</span></span>  
  
### <a name="typeof-used-in-the-constructor"></a><span data-ttu-id="73033-119">typeof utilizado en el constructor</span><span class="sxs-lookup"><span data-stu-id="73033-119">typeof used in the constructor</span></span>  
 <span data-ttu-id="73033-120">Si llama a un constructor de estas clases de serialización e incluye la palabra clave [typeof](~/docs/csharp/language-reference/keywords/typeof.md) de C# en la llamada al método, **no tiene que hacer nada más**.</span><span class="sxs-lookup"><span data-stu-id="73033-120">If you call a constructor of these serialization classes and include the C# [typeof](~/docs/csharp/language-reference/keywords/typeof.md) keyword in the method call, **you do not have to do any additional work**.</span></span> <span data-ttu-id="73033-121">Por ejemplo, en cada una de las siguientes llamadas a un constructor de clase de serialización, la palabra clave `typeof` se utiliza como parte de la expresión que se pasa al constructor.</span><span class="sxs-lookup"><span data-stu-id="73033-121">For example, in each of the following calls to a serialization class constructor, the `typeof` keyword is used as part of the expression passed to the constructor.</span></span>  
  
 [!code-csharp[ProjectN#5](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/serialize1.cs#5)]  
  
 <span data-ttu-id="73033-122">El compilador de [!INCLUDE[net_native](../../../includes/net-native-md.md)] controlará automáticamente este código.</span><span class="sxs-lookup"><span data-stu-id="73033-122">The [!INCLUDE[net_native](../../../includes/net-native-md.md)] compiler will automatically handle this code.</span></span>  
  
### <a name="typeof-used-outside-the-constructor"></a><span data-ttu-id="73033-123">typeof usado fuera del constructor</span><span class="sxs-lookup"><span data-stu-id="73033-123">typeof used outside the constructor</span></span>  
 <span data-ttu-id="73033-124">Si llama a un constructor de estas clases de serialización y usa la palabra clave [typeof](~/docs/csharp/language-reference/keywords/typeof.md) de C# fuera de la expresión proporcionada al parámetro <xref:System.Type> del constructor, como en el código siguiente, el compilador de [!INCLUDE[net_native](../../../includes/net-native-md.md)] no puede resolver el tipo:</span><span class="sxs-lookup"><span data-stu-id="73033-124">If you call a constructor of these serialization classes and use the C# [typeof](~/docs/csharp/language-reference/keywords/typeof.md) keyword outside the expression supplied to the constructor’s <xref:System.Type> parameter, as in the following code, the [!INCLUDE[net_native](../../../includes/net-native-md.md)] compiler cannot resolve the type:</span></span>  
  
 [!code-csharp[ProjectN#6](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/serialize1.cs#6)]  
  
 <span data-ttu-id="73033-125">En este caso, debe especificar el tipo en el archivo de directivas de tiempo de ejecución mediante la adición de una entrada como la siguiente:</span><span class="sxs-lookup"><span data-stu-id="73033-125">In this case, you must specify the type in the runtime directives file by adding an entry like this:</span></span>  
  
```xml  
<Type Name="DataSet" Browse="Required Public" />  
```  
  
 <span data-ttu-id="73033-126">Del mismo modo, si llama a un constructor como <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.Type%5B%5D%29?displayProperty=nameWithType> y proporciona una matriz de objetos <xref:System.Type> adicionales para serializar, como en el código siguiente, el compilador de [!INCLUDE[net_native](../../../includes/net-native-md.md)] no puede resolver estos tipos.</span><span class="sxs-lookup"><span data-stu-id="73033-126">Similarly, if you call a constructor such as <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.Type%5B%5D%29?displayProperty=nameWithType> and provide an array of additional <xref:System.Type> objects to serialize, as in the following code, the [!INCLUDE[net_native](../../../includes/net-native-md.md)] compiler cannot resolve these types.</span></span>  
  
 [!code-csharp[ProjectN#7](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/serialize1.cs#7)]  
  
 <span data-ttu-id="73033-127">Debe agregar entradas como la siguiente para cada tipo en el archivo de directivas de tiempo de ejecución:</span><span class="sxs-lookup"><span data-stu-id="73033-127">You must add entries such as the following for each type to the runtime directives file:</span></span>  
  
```xml  
<Type Name="t" Browse="Required Public" />  
```  
  
 <span data-ttu-id="73033-128">Para más información sobre la sintaxis usada en el ejemplo, vea [Elemento \<Type>](../../../docs/framework/net-native/type-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="73033-128">For information about the syntax used in the example, see [\<Type> Element](../../../docs/framework/net-native/type-element-net-native.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73033-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="73033-129">See also</span></span>

- [<span data-ttu-id="73033-130">Runtime Directives (rd.xml) Configuration File Reference (Referencia del archivo de configuración de directivas en tiempo de ejecución (rd.xml))</span><span class="sxs-lookup"><span data-stu-id="73033-130">Runtime Directives (rd.xml) Configuration File Reference</span></span>](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="73033-131">Runtime Directive Elements (Elementos de directivas en tiempo de ejecución)</span><span class="sxs-lookup"><span data-stu-id="73033-131">Runtime Directive Elements</span></span>](../../../docs/framework/net-native/runtime-directive-elements.md)
- [<span data-ttu-id="73033-132">\<Tipo > elemento</span><span class="sxs-lookup"><span data-stu-id="73033-132">\<Type> Element</span></span>](../../../docs/framework/net-native/type-element-net-native.md)
- [<span data-ttu-id="73033-133">Elemento \<Namespace></span><span class="sxs-lookup"><span data-stu-id="73033-133">\<Namespace> Element</span></span>](../../../docs/framework/net-native/namespace-element-net-native.md)
