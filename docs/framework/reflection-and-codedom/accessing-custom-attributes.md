---
title: Acceso a atributos personalizados
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- custom attributes, accessibility
- attributes [.NET Framework], accessing
- reflection, custom attributes
ms.assetid: 1d8e3398-00d8-47d5-a084-214f9859d3d7
ms.openlocfilehash: a5651e9dc8cf40e737dd523ec5d29e876a9c0765
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130297"
---
# <a name="accessing-custom-attributes"></a><span data-ttu-id="9cf63-102">Acceso a atributos personalizados</span><span class="sxs-lookup"><span data-stu-id="9cf63-102">Accessing Custom Attributes</span></span>
<span data-ttu-id="9cf63-103">Después de asociar atributos a elementos de un programa, puede usar la reflexión para consultar su existencia y sus valores.</span><span class="sxs-lookup"><span data-stu-id="9cf63-103">After attributes have been associated with program elements, reflection can be used to query their existence and values.</span></span> <span data-ttu-id="9cf63-104">En .NET Framework versión 1.0 y 1.1, los atributos personalizados se examinan en el contexto de ejecución.</span><span class="sxs-lookup"><span data-stu-id="9cf63-104">In the .NET Framework version 1.0 and 1.1, custom attributes are examined in the execution context.</span></span> <span data-ttu-id="9cf63-105">.NET Framework versión 2.0 proporciona un nuevo contexto de carga, el contexto de solo reflexión, que puede usarse para examinar el código que no se puede cargar para su ejecución.</span><span class="sxs-lookup"><span data-stu-id="9cf63-105">The .NET Framework version 2.0 provides a new load context, the reflection-only context, which can be used to examine code that cannot be loaded for execution.</span></span>  
  
## <a name="the-reflection-only-context"></a><span data-ttu-id="9cf63-106">Contexto de solo reflexión</span><span class="sxs-lookup"><span data-stu-id="9cf63-106">The Reflection-Only Context</span></span>  
 <span data-ttu-id="9cf63-107">El código cargado en el contexto de solo reflexión no se puede ejecutar.</span><span class="sxs-lookup"><span data-stu-id="9cf63-107">Code loaded into the reflection-only context cannot be executed.</span></span> <span data-ttu-id="9cf63-108">Esto significa que no se pueden crear instancias de atributos personalizados, porque requeriría la ejecución de sus constructores.</span><span class="sxs-lookup"><span data-stu-id="9cf63-108">This means that instances of custom attributes cannot be created, because that would require executing their constructors.</span></span> <span data-ttu-id="9cf63-109">Para cargar y examinar los atributos personalizados en el contexto de solo reflexión, use la clase <xref:System.Reflection.CustomAttributeData>.</span><span class="sxs-lookup"><span data-stu-id="9cf63-109">To load and examine custom attributes in the reflection-only context, use the <xref:System.Reflection.CustomAttributeData> class.</span></span> <span data-ttu-id="9cf63-110">Puede obtener instancias de esta clase mediante la sobrecarga adecuada del método <xref:System.Reflection.CustomAttributeData.GetCustomAttributes%2A?displayProperty=nameWithType> estático.</span><span class="sxs-lookup"><span data-stu-id="9cf63-110">You can obtain instances of this class by using the appropriate overload of the static <xref:System.Reflection.CustomAttributeData.GetCustomAttributes%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="9cf63-111">Vea [Cómo: Cargar ensamblados en el contexto de solo reflexión](how-to-load-assemblies-into-the-reflection-only-context.md).</span><span class="sxs-lookup"><span data-stu-id="9cf63-111">See [How to: Load Assemblies into the Reflection-Only Context](how-to-load-assemblies-into-the-reflection-only-context.md).</span></span>  
  
## <a name="the-execution-context"></a><span data-ttu-id="9cf63-112">Contexto de ejecución</span><span class="sxs-lookup"><span data-stu-id="9cf63-112">The Execution Context</span></span>  
 <span data-ttu-id="9cf63-113">Los principales métodos de reflexión para consultar los atributos en el contexto de ejecución son <xref:System.Reflection.MemberInfo.GetCustomAttributes%2A?displayProperty=nameWithType> y <xref:System.Attribute.GetCustomAttributes%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="9cf63-113">The main reflection methods to query attributes in the execution context are <xref:System.Reflection.MemberInfo.GetCustomAttributes%2A?displayProperty=nameWithType> and <xref:System.Attribute.GetCustomAttributes%2A?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="9cf63-114">La accesibilidad de un atributo personalizado se comprueba con respecto al ensamblado al que está asociado.</span><span class="sxs-lookup"><span data-stu-id="9cf63-114">The accessibility of a custom attribute is checked with respect to the assembly in which it is attached.</span></span> <span data-ttu-id="9cf63-115">Esto equivale a comprobar si un método en un tipo del ensamblado al que está asociado el atributo personalizado puede llamar al constructor del atributo personalizado.</span><span class="sxs-lookup"><span data-stu-id="9cf63-115">This is equivalent to checking whether a method on a type in the assembly in which the custom attribute is attached can call the constructor of the custom attribute.</span></span>  
  
 <span data-ttu-id="9cf63-116">Los métodos como <xref:System.Reflection.Assembly.GetCustomAttributes%28System.Boolean%29?displayProperty=nameWithType> comprueban la visibilidad y la accesibilidad del argumento de tipo.</span><span class="sxs-lookup"><span data-stu-id="9cf63-116">Methods such as <xref:System.Reflection.Assembly.GetCustomAttributes%28System.Boolean%29?displayProperty=nameWithType> check the visibility and accessibility of the type argument.</span></span> <span data-ttu-id="9cf63-117">Solo el código del ensamblado que contiene el tipo definido por el usuario puede recuperar un atributo personalizado de ese tipo mediante **GetCustomAttributes**.</span><span class="sxs-lookup"><span data-stu-id="9cf63-117">Only code in the assembly that contains the user-defined type can retrieve a custom attribute of that type using **GetCustomAttributes**.</span></span>  
  
 <span data-ttu-id="9cf63-118">El siguiente ejemplo de C# es un modelo de diseño típico de atributos personalizados</span><span class="sxs-lookup"><span data-stu-id="9cf63-118">The following C# example is a typical custom attribute design pattern.</span></span> <span data-ttu-id="9cf63-119">en el que se muestra el modelo de reflexión de atributos personalizados en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="9cf63-119">It illustrates the runtime custom attribute reflection model.</span></span>  
  
```csharp
System.DLL  
public class DescriptionAttribute : Attribute  
{  
}  
  
System.Web.DLL  
internal class MyDescriptionAttribute : DescriptionAttribute  
{  
}  
  
public class LocalizationExtenderProvider  
{  
    [MyDescriptionAttribute(...)]  
    public CultureInfo GetLanguage(...)  
    {  
    }  
}  
```  
  
 <span data-ttu-id="9cf63-120">Si el tiempo de ejecución intenta recuperar los atributos personalizados para el tipo de atributo personalizado público <xref:System.ComponentModel.DescriptionAttribute> asociado al método **GetLanguage**, realiza las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="9cf63-120">If the runtime is attempting to retrieve the custom attributes for the public custom attribute type <xref:System.ComponentModel.DescriptionAttribute> attached to the **GetLanguage** method, it performs the following actions:</span></span>  
  
1. <span data-ttu-id="9cf63-121">El tiempo de ejecución comprueba que el argumento de tipo **DescriptionAttribute** de **Type.GetCustomAttributes**(Type *type*) es público y, por tanto, es visible y accesible.</span><span class="sxs-lookup"><span data-stu-id="9cf63-121">The runtime checks that the type argument **DescriptionAttribute** to **Type.GetCustomAttributes**(Type *type*) is public, and therefore is visible and accessible.</span></span>  
  
2. <span data-ttu-id="9cf63-122">El tiempo de ejecución comprueba que el tipo definido por el usuario **MyDescriptionAttribute** que se deriva de **DescriptionAttribute** es visible y accesible en el ensamblado **System.Web.DLL**, donde está asociado al método **GetLanguage**().</span><span class="sxs-lookup"><span data-stu-id="9cf63-122">The runtime checks that the user-defined type **MyDescriptionAttribute** that is derived from **DescriptionAttribute** is visible and accessible within the **System.Web.DLL** assembly, where it is attached to the method **GetLanguage**().</span></span>  
  
3. <span data-ttu-id="9cf63-123">El tiempo de ejecución comprueba que el constructor de **MyDescriptionAttribute** es visible y accesible dentro del ensamblado **System.Web.DLL**.</span><span class="sxs-lookup"><span data-stu-id="9cf63-123">The runtime checks that the constructor of **MyDescriptionAttribute** is visible and accessible within the **System.Web.DLL** assembly.</span></span>  
  
4. <span data-ttu-id="9cf63-124">El tiempo de ejecución llama al constructor de **MyDescriptionAttribute** con los parámetros de atributo personalizados y devuelve el nuevo objeto al llamador.</span><span class="sxs-lookup"><span data-stu-id="9cf63-124">The runtime calls the constructor of **MyDescriptionAttribute** with the custom attribute parameters and returns the new object to the caller.</span></span>  
  
 <span data-ttu-id="9cf63-125">En el modelo de reflexión de atributos personalizados, pueden producirse pérdidas de instancias de tipos definidos por el usuario fuera del ensamblado donde está definido el tipo.</span><span class="sxs-lookup"><span data-stu-id="9cf63-125">The custom attribute reflection model could leak instances of user-defined types outside the assembly in which the type is defined.</span></span> <span data-ttu-id="9cf63-126">Esto no es diferente de los miembros de la biblioteca del sistema en tiempo de ejecución que devuelven instancias de tipos definidos por el usuario, como cuando <xref:System.Type.GetMethods%2A?displayProperty=nameWithType> devuelve una matriz de objetos **RuntimeMethodInfo**.</span><span class="sxs-lookup"><span data-stu-id="9cf63-126">This is no different from the members in the runtime system library that return instances of user-defined types, such as <xref:System.Type.GetMethods%2A?displayProperty=nameWithType> returning an array of **RuntimeMethodInfo** objects.</span></span> <span data-ttu-id="9cf63-127">Para evitar que a un cliente detecte información sobre un tipo de atributo personalizado definido por el usuario, defina los miembros del tipo como no públicos.</span><span class="sxs-lookup"><span data-stu-id="9cf63-127">To prevent a client from discovering information about a user-defined custom attribute type, define the type's members to be nonpublic.</span></span>  
  
 <span data-ttu-id="9cf63-128">En el ejemplo siguiente se muestra la forma básica de usar la reflexión para obtener acceso a atributos personalizados.</span><span class="sxs-lookup"><span data-stu-id="9cf63-128">The following example demonstrates the basic way of using reflection to get access to custom attributes.</span></span>  
  
 [!code-cpp[CustomAttributeData#2](../../../samples/snippets/cpp/VS_Snippets_CLR/CustomAttributeData/CPP/source2.cpp#2)]
 [!code-csharp[CustomAttributeData#2](../../../samples/snippets/csharp/VS_Snippets_CLR/CustomAttributeData/CS/source2.cs#2)]
 [!code-vb[CustomAttributeData#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CustomAttributeData/VB/source2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="9cf63-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="9cf63-129">See also</span></span>

- <xref:System.Reflection.MemberInfo.GetCustomAttributes%2A?displayProperty=nameWithType>
- <xref:System.Attribute.GetCustomAttributes%2A?displayProperty=nameWithType>
- [<span data-ttu-id="9cf63-130">Ver información tipos</span><span class="sxs-lookup"><span data-stu-id="9cf63-130">Viewing Type Information</span></span>](viewing-type-information.md)
- [<span data-ttu-id="9cf63-131">Consideraciones de seguridad sobre la reflexión</span><span class="sxs-lookup"><span data-stu-id="9cf63-131">Security Considerations for Reflection</span></span>](security-considerations-for-reflection.md)
