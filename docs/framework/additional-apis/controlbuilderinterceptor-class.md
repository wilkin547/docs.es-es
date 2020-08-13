---
title: Clase ControlBuilderInterceptor
ms.date: 08/11/2020
api_name:
- System.Web.Compilation.ControlBuilderInterceptor
api_location:
- System.Web.dll
api_type:
- Assembly
topic_type:
- apiref
ms.openlocfilehash: 0cd7409deb9cb84783cfa70600999fa4b2a2d2e2
ms.sourcegitcommit: d337df55f83325918cbbd095eb573400bea49064
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2020
ms.locfileid: "88187984"
---
# <a name="controlbuilderinterceptor-class"></a><span data-ttu-id="08bbd-102">Clase ControlBuilderInterceptor</span><span class="sxs-lookup"><span data-stu-id="08bbd-102">ControlBuilderInterceptor class</span></span>

<span data-ttu-id="08bbd-103">La `ControlBuilderInterceptor` clase permite personalizar o controlar el proceso de compilación.</span><span class="sxs-lookup"><span data-stu-id="08bbd-103">The `ControlBuilderInterceptor` class allows the compilation process to be customized or controlled.</span></span>

## <a name="syntax"></a><span data-ttu-id="08bbd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="08bbd-104">Syntax</span></span>

```csharp
internal class ControlBuilderInterceptor
```

> [!WARNING]
> <span data-ttu-id="08bbd-105">La `ControlBuilderInterceptor` clase es interna y no está diseñada para usarse directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="08bbd-105">The `ControlBuilderInterceptor` class is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="08bbd-106">Tal y como se describe en la sección Comentarios, se puede comprobar la existencia de este tipo para determinar si la compatibilidad con el tipo de interceptor está presente.</span><span class="sxs-lookup"><span data-stu-id="08bbd-106">As described in the Remarks section, the existence of this type can be checked to determine whether interceptor type support is present.</span></span> <span data-ttu-id="08bbd-107">Microsoft no admite ningún otro uso de esta clase en una aplicación de producción bajo ninguna circunstancia.</span><span class="sxs-lookup"><span data-stu-id="08bbd-107">Microsoft does not support any other use of this class in a production application under any circumstance.</span></span>

## <a name="remarks"></a><span data-ttu-id="08bbd-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="08bbd-108">Remarks</span></span>

<span data-ttu-id="08bbd-109">En .NET Framework 2,0 y .NET Framework 3,5, las actualizaciones del [2020 de agosto](https://portal.msrc.microsoft.com/security-guidance/releasenotedetail/2020-Aug) agregaron compatibilidad con el uso de un tipo de interceptor para personalizar o controlar el proceso de compilación.</span><span class="sxs-lookup"><span data-stu-id="08bbd-109">In .NET Framework 2.0 and .NET Framework 3.5, the [August 2020](https://portal.msrc.microsoft.com/security-guidance/releasenotedetail/2020-Aug) updates added support for using an interceptor type to customize or control the compilation process.</span></span> <span data-ttu-id="08bbd-110">Puede determinar si esta compatibilidad está presente mediante <xref:System.Type.GetType?displayProperty=nameWithType> para comprobar la existencia del `ControlBuilderInterceptor` tipo, tal y como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="08bbd-110">You can determine whether this support is present by using <xref:System.Type.GetType?displayProperty=nameWithType> to check the existence of the `ControlBuilderInterceptor` type, as demonstrated in the following code.</span></span>

```csharp
Type type = Type.GetType("System.Web.Compilation.ControlBuilderInterceptor, System.Web, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a");
```

<span data-ttu-id="08bbd-111">Si el valor devuelto no es null, la compatibilidad con el interceptor está presente.</span><span class="sxs-lookup"><span data-stu-id="08bbd-111">If the return value is non-null, then interceptor support is present.</span></span> <span data-ttu-id="08bbd-112">Si el valor devuelto es `null` , o si se produce una excepción, no se han instalado las actualizaciones de agosto de 2020 y la compatibilidad con el interceptor está ausente.</span><span class="sxs-lookup"><span data-stu-id="08bbd-112">If the return value is `null`, or if an exception is thrown, then the August 2020 updates have not been installed, and interceptor support is absent.</span></span>

<span data-ttu-id="08bbd-113">Si la compatibilidad con el interceptor está presente, puede escribir y registrar un tipo de interceptor que interactúe con el proceso de compilación exactamente del mismo modo que lo <xref:System.Web.Compilation.ControlBuilderInterceptor> hace en versiones posteriores de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="08bbd-113">If interceptor support is present, you can write and register an interceptor type that will interact with the compilation process in exactly the same way that <xref:System.Web.Compilation.ControlBuilderInterceptor> does on later versions of .NET Framework.</span></span> <span data-ttu-id="08bbd-114">En .NET Framework 2,0 y .NET Framework 3,5, el tipo de interceptor puede ser cualquier clase que cumpla los requisitos siguientes:</span><span class="sxs-lookup"><span data-stu-id="08bbd-114">In .NET Framework 2.0 and .NET Framework 3.5, the interceptor type can be any class that meets the following requirements:</span></span>

* <span data-ttu-id="08bbd-115">Tiene un constructor público sin parámetros.</span><span class="sxs-lookup"><span data-stu-id="08bbd-115">Has a public, parameterless constructor.</span></span>
* <span data-ttu-id="08bbd-116">Tiene métodos públicos y no estáticos denominados `PreControlBuilderInit` y `OnProcessGeneratedCode` que tienen la misma firma y semántica que los <xref:System.Web.Compilation.ControlBuilderInterceptor.PreControlBuilderInit(System.Web.UI.ControlBuilder,System.Web.UI.TemplateParser,System.Web.UI.ControlBuilder,System.Type,System.String,System.String,System.Collections.IDictionary,System.Collections.IDictionary)> <xref:System.Web.Compilation.ControlBuilderInterceptor.OnProcessGeneratedCode(System.Web.UI.ControlBuilder,System.CodeDom.CodeCompileUnit,System.CodeDom.CodeTypeDeclaration,System.CodeDom.CodeTypeDeclaration,System.CodeDom.CodeMemberMethod,System.CodeDom.CodeMemberMethod,System.Collections.IDictionary)> métodos y, que existen en versiones posteriores de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="08bbd-116">Has public, non-static methods named `PreControlBuilderInit` and `OnProcessGeneratedCode` that have the same signature and semantics as the <xref:System.Web.Compilation.ControlBuilderInterceptor.PreControlBuilderInit(System.Web.UI.ControlBuilder,System.Web.UI.TemplateParser,System.Web.UI.ControlBuilder,System.Type,System.String,System.String,System.Collections.IDictionary,System.Collections.IDictionary)> and <xref:System.Web.Compilation.ControlBuilderInterceptor.OnProcessGeneratedCode(System.Web.UI.ControlBuilder,System.CodeDom.CodeCompileUnit,System.CodeDom.CodeTypeDeclaration,System.CodeDom.CodeTypeDeclaration,System.CodeDom.CodeMemberMethod,System.CodeDom.CodeMemberMethod,System.Collections.IDictionary)> methods, which exist in later versions of .NET Framework.</span></span>

<span data-ttu-id="08bbd-117">Registre el tipo de interceptor mediante la `aspnet:20ControlBuilderInterceptor` clave en la configuración de la aplicación ASP.net ( `<appSettings>` ).</span><span class="sxs-lookup"><span data-stu-id="08bbd-117">Register the interceptor type by using the `aspnet:20ControlBuilderInterceptor` key in ASP.NET application settings (`<appSettings>`).</span></span> <span data-ttu-id="08bbd-118">Esta configuración de aplicación debe aparecer en el equipo o la aplicación *web.config* archivo.</span><span class="sxs-lookup"><span data-stu-id="08bbd-118">This application setting must be listed in your computer or application *web.config* file.</span></span> <span data-ttu-id="08bbd-119">Especifique el tipo de interceptor usando su nombre de tipo calificado con el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="08bbd-119">Specify the interceptor type by using its assembly-qualified type name.</span></span> <span data-ttu-id="08bbd-120">En el ejemplo siguiente se muestra cómo registrar un tipo de interceptor denominado `Fabrikam.Interceptor` .</span><span class="sxs-lookup"><span data-stu-id="08bbd-120">The following example shows how to register an interceptor type named `Fabrikam.Interceptor`.</span></span>

```xml
<configuration>
  ...
  <appSettings>
    ...
    <add key="aspnet:20ControlBuilderInterceptor"
         value="Fabrikam.Interceptor, Fabrikam, Version=1.0.0.0, Culture=neutral, PublicKeyToken=2b3831f2f2b744f7" />
  </appSettings>
</configuration>
```

<span data-ttu-id="08bbd-121">Para recuperar el nombre calificado con el ensamblado de un tipo, utilice la <xref:System.Type.AssemblyQualifiedName?displayProperty=nameWithType> propiedad, como se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="08bbd-121">To retrieve the assembly-qualified name of a type, use the <xref:System.Type.AssemblyQualifiedName?displayProperty=nameWithType> property, as demonstrated in the following code.</span></span>

```csharp
string assemblyQualifiedName = typeof(Fabrikam.Interceptor).AssemblyQualifiedName;
```

<span data-ttu-id="08bbd-122">Cuando existe compatibilidad con el interceptor, el proceso de compilación interactúa con el tipo enumerado de la manera descrita anteriormente.</span><span class="sxs-lookup"><span data-stu-id="08bbd-122">When interceptor support is present, the compilation process interacts with the listed type in the manner described above.</span></span> <span data-ttu-id="08bbd-123">Cuando la compatibilidad con el interceptor está ausente, se omite la configuración de la aplicación y no tiene ningún efecto.</span><span class="sxs-lookup"><span data-stu-id="08bbd-123">When interceptor support is absent, the application setting is ignored and has no effect.</span></span>

## <a name="requirements"></a><span data-ttu-id="08bbd-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="08bbd-124">Requirements</span></span>

<span data-ttu-id="08bbd-125">**Espacio de nombres:** System. Web. Compilation</span><span class="sxs-lookup"><span data-stu-id="08bbd-125">**Namespace:** System.Web.Compilation</span></span>

<span data-ttu-id="08bbd-126">**Ensamblado:** System. Web (en System.Web.dll)</span><span class="sxs-lookup"><span data-stu-id="08bbd-126">**Assembly:** System.Web (in System.Web.dll)</span></span>

<span data-ttu-id="08bbd-127">**.NET Framework versiones:** 3,5, 2,0</span><span class="sxs-lookup"><span data-stu-id="08bbd-127">**.NET Framework versions:** 3.5, 2.0</span></span>
