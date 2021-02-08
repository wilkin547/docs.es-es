---
description: 'Más información sobre: serialización y metadatos'
title: Serialización y metadatos
ms.date: 03/30/2017
ms.assetid: 619ecf1c-1ca5-4d66-8934-62fe7aad78c6
ms.openlocfilehash: da7424d683922618abda4b896bc0e7cf2dbc87be
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801974"
---
# <a name="serialization-and-metadata"></a><span data-ttu-id="05a1b-103">Serialización y metadatos</span><span class="sxs-lookup"><span data-stu-id="05a1b-103">Serialization and Metadata</span></span>

<span data-ttu-id="05a1b-104">Si la aplicación serializa y deserializa objetos, es posible que deba agregar entradas al archivo de directivas en tiempo de ejecución (.rd.xml) para asegurarse de que los metadatos necesarios están presentes en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="05a1b-104">If your app serializes and deserializes objects, you may need to add entries to your runtime directives (.rd.xml) file to ensure that the necessary metadata is present at run time.</span></span> <span data-ttu-id="05a1b-105">Existen dos categorías de serializadores y cada una requiere un tratamiento distinto en el archivo de directivas en tiempo de ejecución:</span><span class="sxs-lookup"><span data-stu-id="05a1b-105">There are two categories of serializers, and each requires different handling in your runtime directives file:</span></span>  
  
- <span data-ttu-id="05a1b-106">Serializadores de terceros basados en la reflexión.</span><span class="sxs-lookup"><span data-stu-id="05a1b-106">Reflection-based third-party serializers.</span></span> <span data-ttu-id="05a1b-107">Estos requieren modificaciones en el archivo de directivas en tiempo de ejecución y se describen en la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="05a1b-107">These require modifications to your runtime directives file, and are discussed in the next section.</span></span>  
  
- <span data-ttu-id="05a1b-108">Los serializadores no basados en reflexión encontrados en la biblioteca de clases de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="05a1b-108">Non-reflection-based serializers found in the .NET Framework class library.</span></span> <span data-ttu-id="05a1b-109">Estos pueden exigir modificaciones en el archivo de directivas en tiempo de ejecución, y se explican en la sección [Serializadores de Microsoft](#Microsoft).</span><span class="sxs-lookup"><span data-stu-id="05a1b-109">These may require modifications to your runtime directives file, and are discussed in the [Microsoft serializers](#Microsoft) section.</span></span>  
  
<a name="ThirdParty"></a>

## <a name="third-party-serializers"></a><span data-ttu-id="05a1b-110">Serializadores de terceros</span><span class="sxs-lookup"><span data-stu-id="05a1b-110">Third-party serializers</span></span>

 <span data-ttu-id="05a1b-111">Los serializadores de terceros, entre los que está Newtonsoft.JSON, normalmente están basados en reflexión.</span><span class="sxs-lookup"><span data-stu-id="05a1b-111">Third-part serializers, including Newtonsoft.JSON, typically are reflection-based.</span></span> <span data-ttu-id="05a1b-112">Dado un objeto binario grande (BLOB) de datos serializados, los campos de los datos se asignan a un tipo concreto mediante la búsqueda por nombre de los campos del tipo de destino.</span><span class="sxs-lookup"><span data-stu-id="05a1b-112">Given a binary large object (BLOB) of serialized data, the fields in the data are assigned to a concrete type by looking up the fields of the target type by name.</span></span> <span data-ttu-id="05a1b-113">Como mínimo, el empleo de estas bibliotecas produce excepciones [MissingMetadataException](missingmetadataexception-class-net-native.md) para cada objeto <xref:System.Type> que se intenta serializar o deserializar en una colección `List<Type>`.</span><span class="sxs-lookup"><span data-stu-id="05a1b-113">At a minimum, using these libraries causes [MissingMetadataException](missingmetadataexception-class-net-native.md) exceptions for each <xref:System.Type> object that you try to serialize or deserialize in a `List<Type>` collection.</span></span>  
  
 <span data-ttu-id="05a1b-114">La forma más sencilla de solucionar los problemas causados por la falta de metadatos para estos serializadores es recopilar los tipos que se utilizarán en la serialización en un único espacio de nombres (como `App.Models`) y aplicar una directiva de metadatos `Serialize`:</span><span class="sxs-lookup"><span data-stu-id="05a1b-114">The easiest way to address issues caused by missing metadata for these serializers is to collect types that will be used in serialization under a single namespace (such as `App.Models`) and apply a `Serialize` metadata directive to it:</span></span>  
  
```xml  
<Namespace Name="App.Models" Serialize="Required PublicAndInternal" />  
```  
  
 <span data-ttu-id="05a1b-115">Para obtener información sobre la sintaxis usada en el ejemplo, vea [ \<Namespace> Element](namespace-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="05a1b-115">For information about the syntax used in the example, see [\<Namespace> Element](namespace-element-net-native.md).</span></span>  
  
<a name="Microsoft"></a>

## <a name="microsoft-serializers"></a><span data-ttu-id="05a1b-116">Serializadores de Microsoft</span><span class="sxs-lookup"><span data-stu-id="05a1b-116">Microsoft serializers</span></span>

 <span data-ttu-id="05a1b-117">Aunque las clases <xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> y <xref:System.Xml.Serialization.XmlSerializer> no se basan en la reflexión, necesitan generar código en función del objeto que se va a serializar o deserializar.</span><span class="sxs-lookup"><span data-stu-id="05a1b-117">Although the <xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>, and <xref:System.Xml.Serialization.XmlSerializer> classes do not rely on reflection, they do require code to be generated based on the object to be serialized or deserialized.</span></span> <span data-ttu-id="05a1b-118">Los constructores sobrecargados de cada serializador incluyen un parámetro <xref:System.Type> que especifica el tipo que se va a serializar o deserializar.</span><span class="sxs-lookup"><span data-stu-id="05a1b-118">The overloaded constructors for each serializer include a <xref:System.Type> parameter that specifies the type to be serialized or deserialized.</span></span> <span data-ttu-id="05a1b-119">La forma de especificar ese tipo en el código define la acción que se debe realizar, como se explica en las dos secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="05a1b-119">How you specify that type in your code defines the action you must take, as discussed in the next two sections.</span></span>  
  
### <a name="typeof-used-in-the-constructor"></a><span data-ttu-id="05a1b-120">typeof utilizado en el constructor</span><span class="sxs-lookup"><span data-stu-id="05a1b-120">typeof used in the constructor</span></span>

 <span data-ttu-id="05a1b-121">Si llama a un constructor de estas clases de serialización e incluye el operador [typeof](../../csharp/language-reference/operators/type-testing-and-cast.md#typeof-operator) de C# en la llamada al método, **no tiene que realizar ningún trabajo adicional**.</span><span class="sxs-lookup"><span data-stu-id="05a1b-121">If you call a constructor of these serialization classes and include the C# [typeof](../../csharp/language-reference/operators/type-testing-and-cast.md#typeof-operator) operator in the method call, **you do not have to do any additional work**.</span></span> <span data-ttu-id="05a1b-122">Por ejemplo, en cada una de las siguientes llamadas a un constructor de clase de serialización, la palabra clave `typeof` se utiliza como parte de la expresión que se pasa al constructor.</span><span class="sxs-lookup"><span data-stu-id="05a1b-122">For example, in each of the following calls to a serialization class constructor, the `typeof` keyword is used as part of the expression passed to the constructor.</span></span>  
  
 [!code-csharp[ProjectN#5](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/serialize1.cs#5)]  
  
 <span data-ttu-id="05a1b-123">El compilador de .NET Native administrará automáticamente este código.</span><span class="sxs-lookup"><span data-stu-id="05a1b-123">The .NET Native compiler will automatically handle this code.</span></span>  
  
### <a name="typeof-used-outside-the-constructor"></a><span data-ttu-id="05a1b-124">typeof usado fuera del constructor</span><span class="sxs-lookup"><span data-stu-id="05a1b-124">typeof used outside the constructor</span></span>

 <span data-ttu-id="05a1b-125">Si se llama a un constructor de estas clases de serialización y se usa el operador [typeof](../../csharp/language-reference/operators/type-testing-and-cast.md#typeof-operator) de C# fuera de la expresión proporcionada al parámetro del constructor <xref:System.Type> , como en el código siguiente, el compilador .net Native no puede resolver el tipo:</span><span class="sxs-lookup"><span data-stu-id="05a1b-125">If you call a constructor of these serialization classes and use the C# [typeof](../../csharp/language-reference/operators/type-testing-and-cast.md#typeof-operator) operator outside the expression supplied to the constructor’s <xref:System.Type> parameter, as in the following code, the .NET Native compiler cannot resolve the type:</span></span>  
  
 [!code-csharp[ProjectN#6](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/serialize1.cs#6)]  
  
 <span data-ttu-id="05a1b-126">En este caso, debe especificar el tipo en el archivo de directivas de tiempo de ejecución mediante la adición de una entrada como la siguiente:</span><span class="sxs-lookup"><span data-stu-id="05a1b-126">In this case, you must specify the type in the runtime directives file by adding an entry like this:</span></span>  
  
```xml  
<Type Name="DataSet" Browse="Required Public" />  
```  
  
 <span data-ttu-id="05a1b-127">Del mismo modo, si llama a un constructor como <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.Type%5B%5D%29> y proporciona una matriz de <xref:System.Type> objetos adicionales para serializar, como en el código siguiente, el compilador .net Native no puede resolver estos tipos.</span><span class="sxs-lookup"><span data-stu-id="05a1b-127">Similarly, if you call a constructor such as <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.Type%5B%5D%29> and provide an array of additional <xref:System.Type> objects to serialize, as in the following code, the .NET Native compiler cannot resolve these types.</span></span>  
  
 [!code-csharp[ProjectN#7](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/serialize1.cs#7)]  
  
<span data-ttu-id="05a1b-128">Agregue entradas como las siguientes para cada tipo al archivo de directivas en tiempo de ejecución:</span><span class="sxs-lookup"><span data-stu-id="05a1b-128">Add entries such as the following for each type to the runtime directives file:</span></span>  
  
```xml  
<Type Name="t" Browse="Required Public" />  
```  
  
<span data-ttu-id="05a1b-129">Para obtener información sobre la sintaxis usada en el ejemplo, vea [ \<Type> Element](type-element-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="05a1b-129">For information about the syntax used in the example, see [\<Type> Element](type-element-net-native.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05a1b-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="05a1b-130">See also</span></span>

- [<span data-ttu-id="05a1b-131">Referencia del archivo de configuración de directivas en tiempo de ejecución (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="05a1b-131">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="05a1b-132">Elementos de directivas en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="05a1b-132">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
- [<span data-ttu-id="05a1b-133">Elemento \<Type></span><span class="sxs-lookup"><span data-stu-id="05a1b-133">\<Type> Element</span></span>](type-element-net-native.md)
- [<span data-ttu-id="05a1b-134">Elemento \<Namespace></span><span class="sxs-lookup"><span data-stu-id="05a1b-134">\<Namespace> Element</span></span>](namespace-element-net-native.md)
