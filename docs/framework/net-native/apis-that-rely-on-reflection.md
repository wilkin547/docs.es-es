---
description: 'Más información sobre: API que dependen de la reflexión'
title: API basada en la reflexión
ms.date: 03/30/2017
ms.assetid: f9532629-6594-4a41-909f-d083f30a42f3
ms.openlocfilehash: a5661719e47a0a9ecb9f0fe9d188b8a67d1068eb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99738746"
---
# <a name="apis-that-rely-on-reflection"></a><span data-ttu-id="53b7f-103">API basada en la reflexión</span><span class="sxs-lookup"><span data-stu-id="53b7f-103">APIs That Rely on Reflection</span></span>

<span data-ttu-id="53b7f-104">En algunos casos, el uso de la reflexión en el código no es obvio y, por tanto, la cadena de herramientas de .NET Native no conserva los metadatos necesarios en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="53b7f-104">In some cases, the use of reflection in code isn't obvious, and so the .NET Native tool chain doesn't preserve metadata that is needed at run time.</span></span> <span data-ttu-id="53b7f-105">En este tema se abordan algunas de las API comunes o patrones de programación habituales que no se consideran parte de la API de reflexión, pero que hacen uso de la reflexión para ejecutarse correctamente.</span><span class="sxs-lookup"><span data-stu-id="53b7f-105">This topic covers some common APIs or common programming patterns that aren't considered part of the reflection API but that rely on reflection to execute successfully.</span></span> <span data-ttu-id="53b7f-106">Si los usa en su código fuente, puede agregar información sobre ellos en el archivo de directivas en tiempo de ejecución (.rd.xml) para que las llamadas a estas API no generen una excepción [MissingMetadataException](missingmetadataexception-class-net-native.md) u otra excepción en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="53b7f-106">If you use them in your source code, you can add information about them to the runtime directives (.rd.xml) file so that calls to these APIs do not throw a [MissingMetadataException](missingmetadataexception-class-net-native.md) exception or some other exception at run time.</span></span>  
  
## <a name="typemakegenerictype-method"></a><span data-ttu-id="53b7f-107">Método Type.MakeGenericType</span><span class="sxs-lookup"><span data-stu-id="53b7f-107">Type.MakeGenericType method</span></span>  

 <span data-ttu-id="53b7f-108">Puede crear dinámicamente instancias de un tipo genérico `AppClass<T>` llamando al método <xref:System.Type.MakeGenericType%2A?displayProperty=nameWithType> mediante código como el siguiente:</span><span class="sxs-lookup"><span data-stu-id="53b7f-108">You can dynamically instantiate a generic type `AppClass<T>` by calling the <xref:System.Type.MakeGenericType%2A?displayProperty=nameWithType> method by using code like this:</span></span>  
  
 [!code-csharp[ProjectN#1](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/type_makegenerictype1.cs#1)]  
  
 <span data-ttu-id="53b7f-109">Para que este código se ejecute correctamente en tiempo de ejecución, son necesarios varios elementos de metadatos.</span><span class="sxs-lookup"><span data-stu-id="53b7f-109">For this code to succeed at run time, several items of metadata are required.</span></span> <span data-ttu-id="53b7f-110">El primero son metadatos de `Browse` para el tipo genérico sin instancia, `AppClass<T>`:</span><span class="sxs-lookup"><span data-stu-id="53b7f-110">The first is `Browse` metadata for the uninstantiated generic type, `AppClass<T>`:</span></span>  
  
```xml  
<Type Name="App1.AppClass`1" Browse="Required PublicAndInternal" />  
```  
  
 <span data-ttu-id="53b7f-111">Esto permite que la llamada al método <xref:System.Type.GetType%28System.String%2CSystem.Boolean%29?displayProperty=nameWithType> se realice correctamente y devuelva un objeto <xref:System.Type> válido.</span><span class="sxs-lookup"><span data-stu-id="53b7f-111">This allows the <xref:System.Type.GetType%28System.String%2CSystem.Boolean%29?displayProperty=nameWithType> method call to succeed and return a valid <xref:System.Type> object.</span></span>  
  
 <span data-ttu-id="53b7f-112">Sin embargo, aun cuando se agreguen metadatos para el tipo genérico sin instancia, la llamada al método <xref:System.Type.MakeGenericType%2A?displayProperty=nameWithType> genera una excepción [MissingMetadataException](missingmetadataexception-class-net-native.md):</span><span class="sxs-lookup"><span data-stu-id="53b7f-112">But even when you add metadata for the uninstantiated generic type, calling the <xref:System.Type.MakeGenericType%2A?displayProperty=nameWithType> method throws a [MissingMetadataException](missingmetadataexception-class-net-native.md) exception:</span></span>  
  
<span data-ttu-id="53b7f-113">Esta operación no se puede realizar porque se quitaron metadatos para el tipo siguiente por razones de rendimiento:</span><span class="sxs-lookup"><span data-stu-id="53b7f-113">This operation cannot be carried out as metadata for the following type was removed for performance reasons:</span></span>  
  
<span data-ttu-id="53b7f-114">`App1.AppClass`1<System. Int32>'.</span><span class="sxs-lookup"><span data-stu-id="53b7f-114">`App1.AppClass`1<System.Int32>\`.</span></span>  
  
 <span data-ttu-id="53b7f-115">Puede incluir la siguiente directiva en tiempo de ejecución al archivo de directivas en tiempo de ejecución para agregar metadatos de `Activate` para la creación específica de instancias sobre `AppClass<T>` de <xref:System.Int32?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="53b7f-115">You can add the following run-time directive to the runtime directives file to add `Activate` metadata for the specific instantiation over `AppClass<T>` of <xref:System.Int32?displayProperty=nameWithType>:</span></span>  
  
```xml  
<TypeInstantiation Name="App1.AppClass" Arguments="System.Int32"
                   Activate="Required Public" />  
```  
  
 <span data-ttu-id="53b7f-116">Cada creación de instancias diferente sobre `AppClass<T>` requiere una directiva particular si se está creando con el método <xref:System.Type.MakeGenericType%2A?displayProperty=nameWithType> y no se usa de forma estática.</span><span class="sxs-lookup"><span data-stu-id="53b7f-116">Each different instantiation over `AppClass<T>` requires a separate directive if it is being created with the <xref:System.Type.MakeGenericType%2A?displayProperty=nameWithType> method and not used statically.</span></span>  
  
## <a name="methodinfomakegenericmethod-method"></a><span data-ttu-id="53b7f-117">Método MethodInfo.MakeGenericMethod</span><span class="sxs-lookup"><span data-stu-id="53b7f-117">MethodInfo.MakeGenericMethod method</span></span>  

 <span data-ttu-id="53b7f-118">Dada una clase `Class1` con un método genérico `GetMethod<T>(T t)`, se puede invocar a `GetMethod` mediante reflexión con código como el siguiente:</span><span class="sxs-lookup"><span data-stu-id="53b7f-118">Given a class `Class1` with a generic method `GetMethod<T>(T t)`, `GetMethod` can be invoked through reflection by using code like this:</span></span>  
  
 [!code-csharp[ProjectN#2](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/makegenericmethod1.cs#2)]  
  
 <span data-ttu-id="53b7f-119">Para ejecutarse correctamente, este código requiere varios elementos de metadatos:</span><span class="sxs-lookup"><span data-stu-id="53b7f-119">To run successfully, this code requires several items of metadata:</span></span>  
  
- <span data-ttu-id="53b7f-120">Metadatos de `Browse` para el tipo cuyo método se quiere llamar.</span><span class="sxs-lookup"><span data-stu-id="53b7f-120">`Browse` metadata for the type whose method you want to call.</span></span>  
  
- <span data-ttu-id="53b7f-121">Metadatos de `Browse` para el método que se quiere llamar.</span><span class="sxs-lookup"><span data-stu-id="53b7f-121">`Browse` metadata for the method you want to call.</span></span>  <span data-ttu-id="53b7f-122">Si se trata de un método público, la adición de metadatos de `Browse` públicos para el tipo contenedor incluye también el método.</span><span class="sxs-lookup"><span data-stu-id="53b7f-122">If it is a public method, adding public `Browse` metadata for the containing type includes the method, too.</span></span>  
  
- <span data-ttu-id="53b7f-123">Metadatos dinámicos para el método al que desea llamar, de modo que la cadena de herramientas de .NET Native no quite el delegado de invocación de reflexión.</span><span class="sxs-lookup"><span data-stu-id="53b7f-123">Dynamic metadata for the method you want to call, so that the reflection invocation delegate is not removed by the .NET Native tool chain.</span></span> <span data-ttu-id="53b7f-124">Si no hay metadatos dinámicos para el método, se generará la siguiente excepción cuando se llame al método <xref:System.Reflection.MethodInfo.MakeGenericMethod%2A?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="53b7f-124">If dynamic metadata is missing for the method, the following exception is thrown when the <xref:System.Reflection.MethodInfo.MakeGenericMethod%2A?displayProperty=nameWithType> method is called:</span></span>  
  
    ```output
    MakeGenericMethod() cannot create this generic method instantiation because the instantiation was not metadata-enabled: 'App1.Class1.GenMethod<Int32>(Int32)'.  
    ```  
  
 <span data-ttu-id="53b7f-125">Las siguientes directivas en tiempo de ejecución procuran que estén disponibles todos los metadatos necesarios:</span><span class="sxs-lookup"><span data-stu-id="53b7f-125">The following runtime directives ensure that all required metadata is available:</span></span>  
  
```xml  
<Type Name="App1.Class1" Browse="Required PublicAndInternal">  
   <MethodInstantiation Name="GenMethod" Arguments="System.Int32" Dynamic="Required"/>  
</Type>  
```  
  
 <span data-ttu-id="53b7f-126">Se necesita una directiva `MethodInstantiation` por cada creación de instancia diferente del método que se invoca dinámicamente, y el elemento `Arguments` se actualiza para reflejar cada argumento de creación de instancia diferente.</span><span class="sxs-lookup"><span data-stu-id="53b7f-126">A `MethodInstantiation` directive is required for each different instantiation of the method that is dynamically invoked, and the `Arguments` element is updated to reflect each different instantiation argument.</span></span>  
  
## <a name="arraycreateinstance-and-typemaketypearray-methods"></a><span data-ttu-id="53b7f-127">Métodos Array.CreateInstance y Type.MakeTypeArray</span><span class="sxs-lookup"><span data-stu-id="53b7f-127">Array.CreateInstance and Type.MakeTypeArray methods</span></span>  

 <span data-ttu-id="53b7f-128">En el siguiente ejemplo se llama a los métodos <xref:System.Type.MakeArrayType%2A?displayProperty=nameWithType> y <xref:System.Array.CreateInstance%2A?displayProperty=nameWithType> en un tipo, `Class1`.</span><span class="sxs-lookup"><span data-stu-id="53b7f-128">The following example calls the <xref:System.Type.MakeArrayType%2A?displayProperty=nameWithType> and <xref:System.Array.CreateInstance%2A?displayProperty=nameWithType> methods on a type, `Class1`.</span></span>  
  
 [!code-csharp[ProjectN#3](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/array1.cs#3)]  
  
 <span data-ttu-id="53b7f-129">Si no hay metadatos de matriz presentes, se produce el siguiente error:</span><span class="sxs-lookup"><span data-stu-id="53b7f-129">If no array metadata is present, the following error results:</span></span>  
  
```output
This operation cannot be carried out as metadata for the following type was removed for performance reasons:  
  
App1.Class1[]  
  
Unfortunately, no further information is available.  
```  
  
 <span data-ttu-id="53b7f-130">Se necesitan metadatos de `Browse` para el tipo de matriz para poder crear instancia de esta dinámicamente.</span><span class="sxs-lookup"><span data-stu-id="53b7f-130">`Browse` metadata for the array type is required to dynamically instantiate it.</span></span>  <span data-ttu-id="53b7f-131">La siguiente directiva en tiempo de ejecución permite la creación dinámica instancias de `Class1[]`.</span><span class="sxs-lookup"><span data-stu-id="53b7f-131">The following runtime directive allows dynamic instantiation of `Class1[]`.</span></span>  
  
```xml  
<Type Name="App1.Class1[]" Browse="Required Public" />  
```  
  
## <a name="see-also"></a><span data-ttu-id="53b7f-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="53b7f-132">See also</span></span>

- [<span data-ttu-id="53b7f-133">Introducción</span><span class="sxs-lookup"><span data-stu-id="53b7f-133">Getting Started</span></span>](getting-started-with-net-native.md)
- [<span data-ttu-id="53b7f-134">Referencia del archivo de configuración de directivas en tiempo de ejecución (rd.xml)</span><span class="sxs-lookup"><span data-stu-id="53b7f-134">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
