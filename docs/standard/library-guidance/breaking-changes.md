---
title: Cambios importantes y las bibliotecas de .NET
description: Prácticas recomendadas para explorar los cambios importantes al crear bibliotecas de. NET.
author: jamesnk
ms.author: mairaw
ms.date: 10/02/2018
ms.openlocfilehash: 83c01fdad7d836877bf692b87eeb0230219ded36
ms.sourcegitcommit: fd8d4587cc26e53f0e27e230d6e27d828ef4306b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2018
ms.locfileid: "49370340"
---
# <a name="breaking-changes"></a><span data-ttu-id="45641-103">Cambios importantes</span><span class="sxs-lookup"><span data-stu-id="45641-103">Breaking changes</span></span>

<span data-ttu-id="45641-104">Es importante para una biblioteca de .NET buscar un equilibrio entre la estabilidad para los usuarios existentes y la innovación para el futuro.</span><span class="sxs-lookup"><span data-stu-id="45641-104">It's important for a .NET library to find a balance between stability for existing users and innovation for the future.</span></span> <span data-ttu-id="45641-105">Obtenga información sobre los creadores de bibliotecas hacia la refactorización y replanteamiento de código hasta que es perfecto, pero importantes de los usuarios existentes tiene un impacto negativo, especialmente para bibliotecas de bajo nivel.</span><span class="sxs-lookup"><span data-stu-id="45641-105">Library authors lean towards refactoring and rethinking code until it's perfect, but breaking your existing users has a negative impact, especially for low-level libraries.</span></span>

## <a name="project-types-and-breaking-changes"></a><span data-ttu-id="45641-106">Tipos de proyecto y los cambios recientes</span><span class="sxs-lookup"><span data-stu-id="45641-106">Project types and breaking changes</span></span>

<span data-ttu-id="45641-107">Uso de una biblioteca de la Comunidad de .NET cambia el efecto de los principales cambios en los usuarios finales.</span><span class="sxs-lookup"><span data-stu-id="45641-107">How a library is used by the .NET community changes the effect of breaking changes on end-user developers.</span></span>

* <span data-ttu-id="45641-108">**Baja y bibliotecas de nivel intermedio** al igual que un analizador serializador, HTML, asignador relacional de objetos de base de datos o marco web son las más afectadas por cambios importantes.</span><span class="sxs-lookup"><span data-stu-id="45641-108">**Low and middle-level libraries** like a serializer, HTML parser, database object-relational mapper, or web framework are the most affected by breaking changes.</span></span>

  <span data-ttu-id="45641-109">Los paquetes de bloques de creación se usan por el usuario final a los desarrolladores crear aplicaciones y otras bibliotecas como dependencias de NuGet.</span><span class="sxs-lookup"><span data-stu-id="45641-109">Building block packages are used by end-user developers to build applications, and by other libraries as NuGet dependencies.</span></span> <span data-ttu-id="45641-110">Por ejemplo, está creando una aplicación y está usando a un cliente de código abierto para llamar a un servicio web.</span><span class="sxs-lookup"><span data-stu-id="45641-110">For example, you're building an application and are using an open-source client to call a web service.</span></span> <span data-ttu-id="45641-111">Una actualización de última hora a una dependencia que usa el cliente no es algo que puede corregir.</span><span class="sxs-lookup"><span data-stu-id="45641-111">A breaking update to a dependency the client uses isn't something you can fix.</span></span> <span data-ttu-id="45641-112">Es el cliente de código abierto que deba cambiarse y no tiene ningún control sobre él.</span><span class="sxs-lookup"><span data-stu-id="45641-112">It's the open-source client that needs to be changed and you have no control over it.</span></span> <span data-ttu-id="45641-113">Tendrá que buscar las versiones compatibles de las bibliotecas o enviar una corrección a la biblioteca de cliente y espere a que una nueva versión.</span><span class="sxs-lookup"><span data-stu-id="45641-113">You have to find compatible versions of the libraries or submit a fix to the client library and wait for a new version.</span></span> <span data-ttu-id="45641-114">La peor situación posible es si desea utilizar dos bibliotecas que dependan de las versiones incompatibles de una biblioteca de terceros.</span><span class="sxs-lookup"><span data-stu-id="45641-114">The worst-case situation is if you want to use two libraries that depend on mutually incompatible versions of a third library.</span></span>

* <span data-ttu-id="45641-115">**Bibliotecas de alto nivel** como un conjunto de aplicaciones de interfaz de usuario, los controles son menos sensibles a cambios importantes.</span><span class="sxs-lookup"><span data-stu-id="45641-115">**High-level libraries** like a suite of UI controls are less sensitive to breaking changes.</span></span>

  <span data-ttu-id="45641-116">Bibliotecas de alto nivel se hace referencia directamente en una aplicación de usuario final.</span><span class="sxs-lookup"><span data-stu-id="45641-116">High-level libraries are directly referenced in an end-user application.</span></span> <span data-ttu-id="45641-117">Si se producen cambios importantes, el desarrollador puede elegir actualizar a la versión más reciente, o puede modificar su aplicación para que funcione con el cambio.</span><span class="sxs-lookup"><span data-stu-id="45641-117">If breaking changes occur, the developer can choose to update to the latest version, or can modify their application to work with the breaking change.</span></span>

<span data-ttu-id="45641-118">**HACER ✔️** piense en cómo se utilizará la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="45641-118">**✔️ DO** think about how your library will be used.</span></span> <span data-ttu-id="45641-119">¿Qué efectos tendrá los cambios importantes en las aplicaciones y bibliotecas que lo usan?</span><span class="sxs-lookup"><span data-stu-id="45641-119">What effect will breaking changes have on applications and libraries that use it?</span></span>

<span data-ttu-id="45641-120">**HACER ✔️** minimizar los cambios importantes al desarrollar una biblioteca de bajo nivel.</span><span class="sxs-lookup"><span data-stu-id="45641-120">**✔️ DO** minimize breaking changes when developing a low-level .NET library.</span></span>

<span data-ttu-id="45641-121">**Considere la posibilidad de ✔️** publicación principal reescritura de una biblioteca como un nuevo paquete de NuGet.</span><span class="sxs-lookup"><span data-stu-id="45641-121">**✔️ CONSIDER** publishing a major rewrite of a library as a new NuGet package.</span></span>

## <a name="types-of-breaking-changes"></a><span data-ttu-id="45641-122">Tipos de cambios importantes</span><span class="sxs-lookup"><span data-stu-id="45641-122">Types of breaking changes</span></span>

<span data-ttu-id="45641-123">Cambios importantes se dividen en categorías diferentes y no son igualmente impactantes.</span><span class="sxs-lookup"><span data-stu-id="45641-123">Breaking changes fall into different categories and aren't equally impactful.</span></span>

### <a name="source-breaking-change"></a><span data-ttu-id="45641-124">Cambio de origen</span><span class="sxs-lookup"><span data-stu-id="45641-124">Source breaking change</span></span>

<span data-ttu-id="45641-125">Un origen de cambio no afecta a la ejecución del programa, pero provocará errores de compilación la próxima vez que se vuelve a compilar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="45641-125">A source breaking change doesn't affect program execution but will cause compilation errors the next time the application is recompiled.</span></span> <span data-ttu-id="45641-126">Por ejemplo, una nueva sobrecarga puede crear ambigüedad en las llamadas de método que anteriormente se encontraban ambiguas o un parámetro cuyo nombre ha cambiado interrumpirá los llamadores que utilizan parámetros con nombre.</span><span class="sxs-lookup"><span data-stu-id="45641-126">For example, a new overload can create an ambiguity in method calls that were unambiguous previously, or a renamed parameter will break callers that use named parameters.</span></span>

```csharp
public class Task
{
    // Adding a type called Task could conflict with System.Threading.Tasks.Task at compilation
}
```

<span data-ttu-id="45641-127">Como un origen de cambio importante solo es perjudicial cuando los desarrolladores compilar sus aplicaciones, es el menos disruptivo cambio importante.</span><span class="sxs-lookup"><span data-stu-id="45641-127">Because a source breaking change is only harmful when developers recompile their applications, it's the least disruptive breaking change.</span></span> <span data-ttu-id="45641-128">Los desarrolladores pueden corregir fácilmente su propio código fuente roto.</span><span class="sxs-lookup"><span data-stu-id="45641-128">Developers can fix their own broken source code easily.</span></span>

### <a name="behavior-breaking-change"></a><span data-ttu-id="45641-129">Cambio de comportamiento</span><span class="sxs-lookup"><span data-stu-id="45641-129">Behavior breaking change</span></span>

<span data-ttu-id="45641-130">Los cambios de comportamiento son el tipo más común de cambio importante: casi cualquier cambio de comportamiento podría afectar a alguien.</span><span class="sxs-lookup"><span data-stu-id="45641-130">Behavior changes are the most common type of breaking change: almost any change in behavior could break someone.</span></span> <span data-ttu-id="45641-131">Cambia a la biblioteca, como las firmas de método, las excepciones que produce o de entrada o salida formatos de datos, podrían todos afectar negativamente a los consumidores de la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="45641-131">Changes to your library, such as method signatures, exceptions thrown or input or output data formats, could all negatively impact your library consumers.</span></span> <span data-ttu-id="45641-132">Si los usuarios se basaban en el comportamiento previamente dañado, incluso una corrección de errores puede calificar como un cambio importante.</span><span class="sxs-lookup"><span data-stu-id="45641-132">Even a bug fix can qualify as a breaking change if users relied on the previously broken behavior.</span></span>

<span data-ttu-id="45641-133">Incorporar características y mejorar los comportamientos incorrectos son algo bueno, pero sin la atención, puede resultar muy difícil para los usuarios existentes que se va a actualizar.</span><span class="sxs-lookup"><span data-stu-id="45641-133">Adding features and improving bad behaviors is a good thing, but without care it can make it very hard for existing users to upgrade.</span></span> <span data-ttu-id="45641-134">Es un enfoque para ayudar a los desarrolladores a lidiar con los últimos cambios de comportamiento ocultarlas detrás de la configuración.</span><span class="sxs-lookup"><span data-stu-id="45641-134">One approach to helping developers deal with behavior breaking changes is to hide them behind settings.</span></span> <span data-ttu-id="45641-135">La configuración permite a los desarrolladores actualizar a la versión más reciente de la biblioteca mientras al mismo tiempo si elige participar o dejar de participar en cambios importantes.</span><span class="sxs-lookup"><span data-stu-id="45641-135">Settings let developers update to the latest version of your library while at the same time choosing to opt in or opt out of breaking changes.</span></span> <span data-ttu-id="45641-136">Esta estrategia permite a los desarrolladores a mantenerse al día al permitir que su código usado adaptarse con el tiempo.</span><span class="sxs-lookup"><span data-stu-id="45641-136">This strategy lets developers stay up to date while letting their consuming code adapt over time.</span></span>

<span data-ttu-id="45641-137">Por ejemplo, ASP.NET Core MVC tiene el concepto de un [versión compatibilidad](/aspnet/core/mvc/compatibility-version) que modifica las características habilitadas y deshabilitadas en `MvcOptions`.</span><span class="sxs-lookup"><span data-stu-id="45641-137">For example, ASP.NET Core MVC has the concept of a [compatibility version](/aspnet/core/mvc/compatibility-version) that modifies the features enabled and disabled on `MvcOptions`.</span></span>

<span data-ttu-id="45641-138">**Considere la posibilidad de ✔️** excluyendo las nuevas características de forma predeterminada, si afectan a los usuarios existentes y permiten que los desarrolladores a participar en la característica con una configuración.</span><span class="sxs-lookup"><span data-stu-id="45641-138">**✔️ CONSIDER** leaving new features off by default, if they affect existing users, and let developers opt in to the feature with a setting.</span></span>

### <a name="binary-breaking-change"></a><span data-ttu-id="45641-139">Cambio importante binario</span><span class="sxs-lookup"><span data-stu-id="45641-139">Binary breaking change</span></span>

<span data-ttu-id="45641-140">Se produce un cambio de archivo binario cuando cambie la API pública de la biblioteca, por lo que los ensamblados compilados con versiones anteriores de la biblioteca ya no sean pueden llamar a la API.</span><span class="sxs-lookup"><span data-stu-id="45641-140">A binary breaking change happens when you change the public API of your library, so assemblies compiled against older versions of your library are no longer able to call the API.</span></span> <span data-ttu-id="45641-141">Por ejemplo, cambiar la firma de un método mediante la adición de un nuevo parámetro hará que los ensamblados compilados con la versión anterior de la biblioteca producir un <xref:System.MissingMethodException>.</span><span class="sxs-lookup"><span data-stu-id="45641-141">For example, changing a method's signature by adding a new parameter will cause assemblies compiled against the older version of the library to throw a <xref:System.MissingMethodException>.</span></span>

<span data-ttu-id="45641-142">Un cambio de archivo binario también puede interrumpir un **todo el ensamblado**.</span><span class="sxs-lookup"><span data-stu-id="45641-142">A binary breaking change can also break an **entire assembly**.</span></span> <span data-ttu-id="45641-143">Cambiar el nombre de un ensamblado con `AssemblyName` cambiará la identidad del ensamblado, así como agregar, quitar o cambiar la clave de nomenclatura segura del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="45641-143">Renaming an assembly with `AssemblyName` will change the assembly's identity, as will adding, removing, or changing the assembly's strong naming key.</span></span> <span data-ttu-id="45641-144">Un cambio de identidad de un ensamblado interrumpirá en todo el código compilado que lo usa.</span><span class="sxs-lookup"><span data-stu-id="45641-144">A change of an assembly's identity will break all compiled code that uses it.</span></span>

<span data-ttu-id="45641-145">**❌ NO** cambiar un nombre de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="45641-145">**❌ DO NOT** change an assembly name.</span></span>

<span data-ttu-id="45641-146">**NO ❌** agregar, quitar o cambiar la clave de nomenclatura segura.</span><span class="sxs-lookup"><span data-stu-id="45641-146">**❌ DO NOT** add, remove, or change the strong naming key.</span></span>

<span data-ttu-id="45641-147">**Considere la posibilidad de ✔️** mediante clases base abstractas en lugar de interfaces.</span><span class="sxs-lookup"><span data-stu-id="45641-147">**✔️ CONSIDER** using abstract base classes instead of interfaces.</span></span>

> <span data-ttu-id="45641-148">Agrega algo a una interfaz hará que los tipos existentes que implementan un error.</span><span class="sxs-lookup"><span data-stu-id="45641-148">Adding anything to an interface will cause existing types that implement it to fail.</span></span> <span data-ttu-id="45641-149">Una clase base abstracta permite agregar una implementación virtual predeterminada.</span><span class="sxs-lookup"><span data-stu-id="45641-149">An abstract base class allows you to add a default virtual implementation.</span></span>

<span data-ttu-id="45641-150">**Considere la posibilidad de ✔️** colocar el <xref:System.ObsoleteAttribute> en tipos y miembros que se va a quitar.</span><span class="sxs-lookup"><span data-stu-id="45641-150">**✔️ CONSIDER** placing the <xref:System.ObsoleteAttribute> on types and members that you intend to remove.</span></span> <span data-ttu-id="45641-151">El atributo debe tener instrucciones para actualizar el código para dejar de usar la API obsoleta.</span><span class="sxs-lookup"><span data-stu-id="45641-151">The attribute should have instructions for updating code to no longer use the obsolete API.</span></span>

> <span data-ttu-id="45641-152">Código que llama a tipos y métodos con el <xref:System.ObsoleteAttribute> generará una advertencia de compilación con el mensaje proporcionado para el atributo.</span><span class="sxs-lookup"><span data-stu-id="45641-152">Code that calls types and methods with the <xref:System.ObsoleteAttribute> will generate a build warning with the message supplied to the attribute.</span></span> <span data-ttu-id="45641-153">Las personas de dar advertencias que use el tiempo de superficie de API obsoleto para migrar de modo que cuando se quita la API obsoleta, la mayoría ya no está usando.</span><span class="sxs-lookup"><span data-stu-id="45641-153">The warnings give people who use the obsolete API surface time to migrate so that when the obsolete API is removed, most are no longer using it.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="45641-154">Vea también</span><span class="sxs-lookup"><span data-stu-id="45641-154">See also</span></span>

* [<span data-ttu-id="45641-155">Consideraciones sobre la versión y actualización para los desarrolladores de C#</span><span class="sxs-lookup"><span data-stu-id="45641-155">Version and update considerations for C# developers</span></span>](../../csharp/whats-new/version-update-considerations.md)
* [<span data-ttu-id="45641-156">Una guía definitiva para cambios importantes de la API de .NET</span><span class="sxs-lookup"><span data-stu-id="45641-156">A definitive guide to API-breaking changes in .NET</span></span>](https://stackoverflow.com/questions/1456785/a-definitive-guide-to-api-breaking-changes-in-net)
* [<span data-ttu-id="45641-157">Reglas de cambio de salto de CoreFX</span><span class="sxs-lookup"><span data-stu-id="45641-157">CoreFX Breaking Change Rules</span></span>](https://github.com/dotnet/corefx/blob/master/Documentation/coding-guidelines/breaking-change-rules.md)

>[!div class="step-by-step"]
[<span data-ttu-id="45641-158">Anterior</span><span class="sxs-lookup"><span data-stu-id="45641-158">Previous</span></span>](./versioning.md)
