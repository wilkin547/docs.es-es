---
title: Cambios importantes y las bibliotecas de .NET
description: Procedimientos recomendados para explorar los cambios importantes al crear bibliotecas de .NET.
ms.date: 10/02/2018
ms.openlocfilehash: 8536662ae1cd9733efbcc0c6526bd69d34a13177
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740982"
---
# <a name="breaking-changes"></a><span data-ttu-id="c4ff3-103">Cambios importantes</span><span class="sxs-lookup"><span data-stu-id="c4ff3-103">Breaking changes</span></span>

<span data-ttu-id="c4ff3-104">Es importante para una biblioteca de .NET buscar el equilibrio entre la estabilidad para los usuarios existentes y la innovación para el futuro.</span><span class="sxs-lookup"><span data-stu-id="c4ff3-104">It's important for a .NET library to find a balance between stability for existing users and innovation for the future.</span></span> <span data-ttu-id="c4ff3-105">Los creadores de bibliotecas tienden a la refactorización y el replanteamiento de código hasta que es perfecto, pero realizar cambios importantes que afectan a los usuarios existentes tiene un impacto negativo, especialmente para bibliotecas de bajo nivel.</span><span class="sxs-lookup"><span data-stu-id="c4ff3-105">Library authors lean towards refactoring and rethinking code until it's perfect, but breaking your existing users has a negative impact, especially for low-level libraries.</span></span>

## <a name="project-types-and-breaking-changes"></a><span data-ttu-id="c4ff3-106">Tipos de proyecto y cambios importantes</span><span class="sxs-lookup"><span data-stu-id="c4ff3-106">Project types and breaking changes</span></span>

<span data-ttu-id="c4ff3-107">El uso que la comunidad de .NET realiza de una biblioteca cambia el efecto de los cambios importantes en los usuarios finales.</span><span class="sxs-lookup"><span data-stu-id="c4ff3-107">How a library is used by the .NET community changes the effect of breaking changes on end-user developers.</span></span>

- <span data-ttu-id="c4ff3-108">**Las bibliotecas de nivel bajo e intermedio**, como un serializador, un analizador de HTML, un asignador relacional de objetos de base de datos o un marco web, son las más afectadas por cambios importantes.</span><span class="sxs-lookup"><span data-stu-id="c4ff3-108">**Low and middle-level libraries** like a serializer, HTML parser, database object-relational mapper, or web framework are the most affected by breaking changes.</span></span>

  <span data-ttu-id="c4ff3-109">Los usuarios finales y otras bibliotecas como dependencias de NuGet usan los paquetes de bloques de creación para desarrollar aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="c4ff3-109">Building block packages are used by end-user developers to build applications, and by other libraries as NuGet dependencies.</span></span> <span data-ttu-id="c4ff3-110">Por ejemplo, está creando una aplicación y está usando a un cliente de código abierto para llamar a un servicio web.</span><span class="sxs-lookup"><span data-stu-id="c4ff3-110">For example, you're building an application and are using an open-source client to call a web service.</span></span> <span data-ttu-id="c4ff3-111">Una actualización importante a una dependencia que usa el cliente no es algo que pueda solucionar.</span><span class="sxs-lookup"><span data-stu-id="c4ff3-111">A breaking update to a dependency the client uses isn't something you can fix.</span></span> <span data-ttu-id="c4ff3-112">Debería cambiarse el cliente de código abierto y no tiene control sobre él.</span><span class="sxs-lookup"><span data-stu-id="c4ff3-112">It's the open-source client that needs to be changed and you have no control over it.</span></span> <span data-ttu-id="c4ff3-113">Tendrá que buscar versiones compatibles de las bibliotecas o enviar una corrección a la biblioteca de cliente y esperar a una nueva versión.</span><span class="sxs-lookup"><span data-stu-id="c4ff3-113">You have to find compatible versions of the libraries or submit a fix to the client library and wait for a new version.</span></span> <span data-ttu-id="c4ff3-114">La peor situación posible es si quiere usar dos bibliotecas que dependen de versiones incompatibles de una biblioteca de terceros.</span><span class="sxs-lookup"><span data-stu-id="c4ff3-114">The worst-case situation is if you want to use two libraries that depend on mutually incompatible versions of a third library.</span></span>

- <span data-ttu-id="c4ff3-115">**Las bibliotecas generales** como un conjunto de controles de IU, son menos sensibles a los cambios importantes.</span><span class="sxs-lookup"><span data-stu-id="c4ff3-115">**High-level libraries** like a suite of UI controls are less sensitive to breaking changes.</span></span>

  <span data-ttu-id="c4ff3-116">En las aplicaciones de usuario final se hace referencia directa a las bibliotecas generales.</span><span class="sxs-lookup"><span data-stu-id="c4ff3-116">High-level libraries are directly referenced in an end-user application.</span></span> <span data-ttu-id="c4ff3-117">Si se producen cambios importantes, el desarrollador puede elegir si quiere actualizar a la versión más reciente o puede modificar su aplicación para que funcione con el cambio.</span><span class="sxs-lookup"><span data-stu-id="c4ff3-117">If breaking changes occur, the developer can choose to update to the latest version, or can modify their application to work with the breaking change.</span></span>

<span data-ttu-id="c4ff3-118">**✔️ PIENSE** en cómo se utilizará la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="c4ff3-118">**✔️ DO** think about how your library will be used.</span></span> <span data-ttu-id="c4ff3-119">¿Qué efectos tendrán los cambios importantes en las aplicaciones y bibliotecas que la usan?</span><span class="sxs-lookup"><span data-stu-id="c4ff3-119">What effect will breaking changes have on applications and libraries that use it?</span></span>

<span data-ttu-id="c4ff3-120">**✔️ MINIMICE** los cambios importantes al desarrollar una biblioteca de .NET de bajo nivel.</span><span class="sxs-lookup"><span data-stu-id="c4ff3-120">**✔️ DO** minimize breaking changes when developing a low-level .NET library.</span></span>

<span data-ttu-id="c4ff3-121">**✔️ ES RECOMENDABLE** publicar una reescritura importante de una biblioteca como un nuevo paquete NuGet.</span><span class="sxs-lookup"><span data-stu-id="c4ff3-121">**✔️ CONSIDER** publishing a major rewrite of a library as a new NuGet package.</span></span>

## <a name="types-of-breaking-changes"></a><span data-ttu-id="c4ff3-122">Tipos de cambios importantes</span><span class="sxs-lookup"><span data-stu-id="c4ff3-122">Types of breaking changes</span></span>

<span data-ttu-id="c4ff3-123">Los cambios importantes se dividen en categorías diferentes y no tienen el mismo impacto.</span><span class="sxs-lookup"><span data-stu-id="c4ff3-123">Breaking changes fall into different categories and aren't equally impactful.</span></span>

### <a name="source-breaking-change"></a><span data-ttu-id="c4ff3-124">Cambios importantes del código fuente</span><span class="sxs-lookup"><span data-stu-id="c4ff3-124">Source breaking change</span></span>

<span data-ttu-id="c4ff3-125">Un cambio importante del código fuente no afecta a la ejecución del programa, pero provocará errores de compilación la próxima vez que se vuelva a compilar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="c4ff3-125">A source breaking change doesn't affect program execution but will cause compilation errors the next time the application is recompiled.</span></span> <span data-ttu-id="c4ff3-126">Por ejemplo, una nueva sobrecarga puede crear ambigüedad en las llamadas de método que anteriormente no eran ambiguas o un parámetro cuyo nombre ha cambiado interrumpirá a los autores de la llamada que usan parámetros con nombre.</span><span class="sxs-lookup"><span data-stu-id="c4ff3-126">For example, a new overload can create an ambiguity in method calls that were unambiguous previously, or a renamed parameter will break callers that use named parameters.</span></span>

```csharp
public class Task
{
    // Adding a type called Task could conflict with System.Threading.Tasks.Task at compilation
}
```

<span data-ttu-id="c4ff3-127">Como un cambio importante de código fuente solo es perjudicial cuando los desarrolladores vuelven a compilar sus aplicaciones, es el cambio importante menos disruptivo.</span><span class="sxs-lookup"><span data-stu-id="c4ff3-127">Because a source breaking change is only harmful when developers recompile their applications, it's the least disruptive breaking change.</span></span> <span data-ttu-id="c4ff3-128">Los desarrolladores pueden corregir fácilmente su propio código fuente roto.</span><span class="sxs-lookup"><span data-stu-id="c4ff3-128">Developers can fix their own broken source code easily.</span></span>

### <a name="behavior-breaking-change"></a><span data-ttu-id="c4ff3-129">Cambios importantes del comportamiento</span><span class="sxs-lookup"><span data-stu-id="c4ff3-129">Behavior breaking change</span></span>

<span data-ttu-id="c4ff3-130">Los cambios de comportamiento son el tipo más común de cambio importante: casi cualquier cambio de comportamiento podría afectar a alguien.</span><span class="sxs-lookup"><span data-stu-id="c4ff3-130">Behavior changes are the most common type of breaking change: almost any change in behavior could break someone.</span></span> <span data-ttu-id="c4ff3-131">Los cambios a la biblioteca, como las firmas de método, las excepciones que se producen o los formatos de datos de entrada o salida, podrían afectar negativamente a los consumidores de la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="c4ff3-131">Changes to your library, such as method signatures, exceptions thrown or input or output data formats, could all negatively impact your library consumers.</span></span> <span data-ttu-id="c4ff3-132">Incluso la corrección de un error podría ser un cambio importante si los usuarios se basaban en el comportamiento con errores anterior.</span><span class="sxs-lookup"><span data-stu-id="c4ff3-132">Even a bug fix can qualify as a breaking change if users relied on the previously broken behavior.</span></span>

<span data-ttu-id="c4ff3-133">La incorporación de características y la mejora de comportamientos incorrectos es algo bueno, pero si no se trata con cuidado, realizar la actualización puede resultar muy difícil para los usuarios existentes.</span><span class="sxs-lookup"><span data-stu-id="c4ff3-133">Adding features and improving bad behaviors is a good thing, but without care it can make it very hard for existing users to upgrade.</span></span> <span data-ttu-id="c4ff3-134">Un enfoque para ayudar a los desarrolladores a lidiar con los últimos cambios importantes de comportamiento es ocultarlos en la configuración.</span><span class="sxs-lookup"><span data-stu-id="c4ff3-134">One approach to helping developers deal with behavior breaking changes is to hide them behind settings.</span></span> <span data-ttu-id="c4ff3-135">La configuración permite a los desarrolladores actualizar a la versión más reciente de la biblioteca y al mismo tiempo utilizar o prescindir de los cambios importantes.</span><span class="sxs-lookup"><span data-stu-id="c4ff3-135">Settings let developers update to the latest version of your library while at the same time choosing to opt in or opt out of breaking changes.</span></span> <span data-ttu-id="c4ff3-136">Esta estrategia permite a los desarrolladores mantenerse al día al mismo tiempo que permiten que el código que usan se adapte con el tiempo.</span><span class="sxs-lookup"><span data-stu-id="c4ff3-136">This strategy lets developers stay up to date while letting their consuming code adapt over time.</span></span>

<span data-ttu-id="c4ff3-137">Por ejemplo, ASP.NET Core MVC tiene el concepto de una [versión de compatibilidad](/aspnet/core/mvc/compatibility-version) que modifica las características habilitadas y deshabilitadas en `MvcOptions`.</span><span class="sxs-lookup"><span data-stu-id="c4ff3-137">For example, ASP.NET Core MVC has the concept of a [compatibility version](/aspnet/core/mvc/compatibility-version) that modifies the features enabled and disabled on `MvcOptions`.</span></span>

<span data-ttu-id="c4ff3-138">**✔️ ES RECOMENDABLE** excluir las nuevas características de forma predeterminada, si afectan a los usuarios existentes, y permitir que los desarrolladores usen la característica con una configuración.</span><span class="sxs-lookup"><span data-stu-id="c4ff3-138">**✔️ CONSIDER** leaving new features off by default, if they affect existing users, and let developers opt in to the feature with a setting.</span></span>

### <a name="binary-breaking-change"></a><span data-ttu-id="c4ff3-139">Cambios importantes de archivo binario</span><span class="sxs-lookup"><span data-stu-id="c4ff3-139">Binary breaking change</span></span>

<span data-ttu-id="c4ff3-140">Un cambio importante de archivo binario se produce al cambiar la API pública de la biblioteca, ya que los ensamblados compilados con versiones anteriores de la biblioteca ya no pueden llamar a la API.</span><span class="sxs-lookup"><span data-stu-id="c4ff3-140">A binary breaking change happens when you change the public API of your library, so assemblies compiled against older versions of your library are no longer able to call the API.</span></span> <span data-ttu-id="c4ff3-141">Por ejemplo, cambiar la firma de un método mediante la adición de un nuevo parámetro hará que los ensamblados compilados con la versión anterior de la biblioteca inicien una excepción <xref:System.MissingMethodException>.</span><span class="sxs-lookup"><span data-stu-id="c4ff3-141">For example, changing a method's signature by adding a new parameter will cause assemblies compiled against the older version of the library to throw a <xref:System.MissingMethodException>.</span></span>

<span data-ttu-id="c4ff3-142">Un cambio importante de archivo binario también puede afectar a un **ensamblado completo**.</span><span class="sxs-lookup"><span data-stu-id="c4ff3-142">A binary breaking change can also break an **entire assembly**.</span></span> <span data-ttu-id="c4ff3-143">Cambiar el nombre de un ensamblado con `AssemblyName` cambiará la identidad del ensamblado, como lo hará agregar, quitar o cambiar la clave de nomenclatura segura del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="c4ff3-143">Renaming an assembly with `AssemblyName` will change the assembly's identity, as will adding, removing, or changing the assembly's strong naming key.</span></span> <span data-ttu-id="c4ff3-144">Un cambio de identidad de un ensamblado afectará a todo el código compilado que lo usa.</span><span class="sxs-lookup"><span data-stu-id="c4ff3-144">A change of an assembly's identity will break all compiled code that uses it.</span></span>

<span data-ttu-id="c4ff3-145">**❌ NO** cambie el nombre de un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="c4ff3-145">**❌ DO NOT** change an assembly name.</span></span>

<span data-ttu-id="c4ff3-146">**❌ NO** agregue, quite o cambie la clave de nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="c4ff3-146">**❌ DO NOT** add, remove, or change the strong naming key.</span></span>

<span data-ttu-id="c4ff3-147">**✔️ ES RECOMENDABLE** usar clases base abstractas en lugar de interfaces.</span><span class="sxs-lookup"><span data-stu-id="c4ff3-147">**✔️ CONSIDER** using abstract base classes instead of interfaces.</span></span>

> <span data-ttu-id="c4ff3-148">La adición de algo a una interfaz hará que se produzca un error de los tipos existentes que la implementan.</span><span class="sxs-lookup"><span data-stu-id="c4ff3-148">Adding anything to an interface will cause existing types that implement it to fail.</span></span> <span data-ttu-id="c4ff3-149">Una clase base abstracta permite agregar una implementación virtual predeterminada.</span><span class="sxs-lookup"><span data-stu-id="c4ff3-149">An abstract base class allows you to add a default virtual implementation.</span></span>

<span data-ttu-id="c4ff3-150">**✔️ ES RECOMENDABLE** colocar el <xref:System.ObsoleteAttribute> en tipos y miembros que vaya a quitar.</span><span class="sxs-lookup"><span data-stu-id="c4ff3-150">**✔️ CONSIDER** placing the <xref:System.ObsoleteAttribute> on types and members that you intend to remove.</span></span> <span data-ttu-id="c4ff3-151">El atributo debe tener instrucciones para actualizar el código para dejar de usar la API obsoleta.</span><span class="sxs-lookup"><span data-stu-id="c4ff3-151">The attribute should have instructions for updating code to no longer use the obsolete API.</span></span>

> <span data-ttu-id="c4ff3-152">El código que llama a tipos y métodos con el <xref:System.ObsoleteAttribute> generará una advertencia de compilación con el mensaje proporcionado al atributo.</span><span class="sxs-lookup"><span data-stu-id="c4ff3-152">Code that calls types and methods with the <xref:System.ObsoleteAttribute> will generate a build warning with the message supplied to the attribute.</span></span> <span data-ttu-id="c4ff3-153">Las advertencias proporcionan tiempo suficiente a los usuarios de la API obsoleta para realizar una migración, de modo que cuando se quite la API obsoleta, la mayoría ya no la estará usando.</span><span class="sxs-lookup"><span data-stu-id="c4ff3-153">The warnings give people who use the obsolete API surface time to migrate so that when the obsolete API is removed, most are no longer using it.</span></span>

```csharp
public class Document
{
    [Obsolete("LoadDocument(string) is obsolete. Use LoadDocument(Uri) instead.")]
    public static Document LoadDocument(string uri)
    {
        return LoadDocument(new Uri(uri));
    }

    public static Document LoadDocument(Uri uri)
    {
        // Load the document
    }
}
```

<span data-ttu-id="c4ff3-154">**✔️ ES RECOMENDABLE** mantener tipos y métodos con el <xref:System.ObsoleteAttribute> indefinidamente en las bibliotecas de nivel medio y bajo.</span><span class="sxs-lookup"><span data-stu-id="c4ff3-154">**✔️ CONSIDER** keeping types and methods with the <xref:System.ObsoleteAttribute> indefinitely in low and middle-level libraries.</span></span>

> <span data-ttu-id="c4ff3-155">Quitar API es un cambio de archivo binario.</span><span class="sxs-lookup"><span data-stu-id="c4ff3-155">Removing APIs is a binary breaking change.</span></span> <span data-ttu-id="c4ff3-156">Es recomendable mantener métodos y tipos obsoletos si su mantenimiento es de bajo coste y no agrega mucha deuda técnica a la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="c4ff3-156">Considering keeping obsolete types and methods if maintaining them is low cost and doesn't add lot of technical debt to your library.</span></span> <span data-ttu-id="c4ff3-157">No quitar tipos y métodos puede ayudar a evitar los peores casos mencionados anteriormente.</span><span class="sxs-lookup"><span data-stu-id="c4ff3-157">Not removing types and methods can help avoid the worst-case scenarios mentioned above.</span></span>

## <a name="see-also"></a><span data-ttu-id="c4ff3-158">Vea también</span><span class="sxs-lookup"><span data-stu-id="c4ff3-158">See also</span></span>

- [<span data-ttu-id="c4ff3-159">Consideraciones sobre versiones y actualizaciones para desarrolladores de C#</span><span class="sxs-lookup"><span data-stu-id="c4ff3-159">Version and update considerations for C# developers</span></span>](../../csharp/whats-new/version-update-considerations.md)
- <span data-ttu-id="c4ff3-160">[A definitive guide to API-breaking changes in .NET](https://stackoverflow.com/questions/1456785/a-definitive-guide-to-api-breaking-changes-in-net) (Una guía definitiva para cambios importantes de API en .NET)</span><span class="sxs-lookup"><span data-stu-id="c4ff3-160">[A definitive guide to API-breaking changes in .NET](https://stackoverflow.com/questions/1456785/a-definitive-guide-to-api-breaking-changes-in-net)</span></span>
- [<span data-ttu-id="c4ff3-161">Reglas de cambios importantes de .NET</span><span class="sxs-lookup"><span data-stu-id="c4ff3-161">.NET breaking change rules</span></span>](https://github.com/dotnet/runtime/blob/master/docs/coding-guidelines/breaking-change-rules.md)

>[!div class="step-by-step"]
>[<span data-ttu-id="c4ff3-162">Anterior</span><span class="sxs-lookup"><span data-stu-id="c4ff3-162">Previous</span></span>](versioning.md)
