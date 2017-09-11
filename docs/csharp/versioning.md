---
title: "Control de versiones de C#: Guía de C#"
description: "Comprender cómo funciona el control de versiones en C# y .NET"
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.date: 01/08/2017
ms.topic: article
ms.prod: visual-studio-dev-14
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: aa8732d7-5cd0-46e1-994a-78017f20d861
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 0b671333019c00abafcfb72533e30936f8fc6ad7
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---

# <a name="versioning-in-c"></a><span data-ttu-id="caef0-104">Control de versiones en C#</span><span class="sxs-lookup"><span data-stu-id="caef0-104">Versioning in C#</span></span> #

<span data-ttu-id="caef0-105">En este tutorial, obtendrá información sobre qué significa el control de versiones en .NET.</span><span class="sxs-lookup"><span data-stu-id="caef0-105">In this tutorial you'll learn what versioning means in .NET.</span></span> <span data-ttu-id="caef0-106">También obtendrá información sobre los factores que deben tenerse en cuenta para controlar las versiones de su biblioteca así como para actualizar a una versión nueva de esta.</span><span class="sxs-lookup"><span data-stu-id="caef0-106">You'll also learn the factors to consider when versioning your library as well as upgrading to a new version of the a library.</span></span>

## <a name="authoring-libraries"></a><span data-ttu-id="caef0-107">Creación de bibliotecas</span><span class="sxs-lookup"><span data-stu-id="caef0-107">Authoring Libraries</span></span>

<span data-ttu-id="caef0-108">Como desarrollador que ha creado bibliotecas de .NET para uso público, probablemente se ha encontrado en situaciones en las que tiene que implementar nuevas actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="caef0-108">As a developer who has created .NET libraries for public use, you've most likely been in situations where you have to roll out new updates.</span></span> <span data-ttu-id="caef0-109">Cómo realizar este proceso es muy importante, ya que necesita asegurarse de que existe una transición sin problemas del código existente a la versión nueva de su biblioteca.</span><span class="sxs-lookup"><span data-stu-id="caef0-109">How you go about this process matters a lot as you need to ensure that there's a seamless transition of existing code to the new version of your library.</span></span> <span data-ttu-id="caef0-110">Aquí se muestran algunos aspectos para tener en cuenta a la hora de crear una versión nueva:</span><span class="sxs-lookup"><span data-stu-id="caef0-110">Here are several things to consider when creating a new release:</span></span>

### <a name="semantic-versioning"></a><span data-ttu-id="caef0-111">Control de versiones semántico</span><span class="sxs-lookup"><span data-stu-id="caef0-111">Semantic Versioning</span></span>

<span data-ttu-id="caef0-112">[Control de versiones semántico](http://semver.org/) (SemVer para abreviar) es una convención de nomenclatura que se aplica a las versiones de su biblioteca para indicar eventos importantes específicos.</span><span class="sxs-lookup"><span data-stu-id="caef0-112">[Semantic versioning](http://semver.org/) (SemVer for short) is a naming convention applied to versions of your library to signify specific milestone events.</span></span>
<span data-ttu-id="caef0-113">De manera ideal, la información de la versión que proporciona a la biblioteca debe ayudar a los desarrolladores a determinar la compatibilidad con sus proyectos que usan versiones anteriores de la misma biblioteca.</span><span class="sxs-lookup"><span data-stu-id="caef0-113">Ideally, the version information you give your library should help developers determine the compatibility with their projects that make use of older versions of that same library.</span></span>

<span data-ttu-id="caef0-114">El enfoque más sencillo de SemVer es el formato de 3 componentes `MAJOR.MINOR.PATCH`, donde:</span><span class="sxs-lookup"><span data-stu-id="caef0-114">The most basic approach to SemVer is the 3 component format `MAJOR.MINOR.PATCH`, where:</span></span>
 
* <span data-ttu-id="caef0-115">`MAJOR` se incrementa cuando realiza cambios de API incompatibles</span><span class="sxs-lookup"><span data-stu-id="caef0-115">`MAJOR` is incremented when you make incompatible API changes</span></span>
* <span data-ttu-id="caef0-116">`MINOR` se incrementa cuando agrega funciones de manera compatible con versiones anteriores</span><span class="sxs-lookup"><span data-stu-id="caef0-116">`MINOR` is incremented when you add functionality in a backwards-compatible manner</span></span>
* <span data-ttu-id="caef0-117">`PATCH` se incrementa cuando realiza correcciones de errores compatibles con versiones anteriores</span><span class="sxs-lookup"><span data-stu-id="caef0-117">`PATCH` is incremented when you make backwards-compatible bug fixes</span></span>

<span data-ttu-id="caef0-118">También existen maneras de especificar otros escenarios como versiones preliminares, etc. al aplicar información de la versión a su biblioteca .NET.</span><span class="sxs-lookup"><span data-stu-id="caef0-118">There are also ways to specify other scenarios like pre-release versions etc. when applying version information to your .NET library.</span></span>

### <a name="backwards-compatibility"></a><span data-ttu-id="caef0-119">Compatibilidad con versiones anteriores</span><span class="sxs-lookup"><span data-stu-id="caef0-119">Backwards Compatibility</span></span>

<span data-ttu-id="caef0-120">A medida que presente versiones nuevas de su biblioteca, la compatibilidad con las versiones anteriores será probablemente una de sus mayores preocupaciones.</span><span class="sxs-lookup"><span data-stu-id="caef0-120">As you release new versions of your library, backwards compatibility with previous versions will most likely be one of your major concerns.</span></span>
<span data-ttu-id="caef0-121">Una versión nueva de su biblioteca es compatible en su origen con una versión anterior si el código que depende de la versión anterior, puede, cuando se vuelve a compilar, trabajar con la versión nueva.</span><span class="sxs-lookup"><span data-stu-id="caef0-121">A new version of your library is source compatible with a previous version if code that depends on the previous version can, when recompiled, work with the new version.</span></span> <span data-ttu-id="caef0-122">Una versión nueva de su biblioteca tiene compatibilidad binaria si una aplicación que dependía de la versión anterior, puede, sin que se vuelva a compilar, trabajar con la versión nueva.</span><span class="sxs-lookup"><span data-stu-id="caef0-122">A new version of your library is binary compatible if an application that depended on the old version can, without recompilation, work with the new version.</span></span>

<span data-ttu-id="caef0-123">Aquí se muestran algunos aspectos a tener en cuenta al intentar mantener la compatibilidad con versiones anteriores de su biblioteca:</span><span class="sxs-lookup"><span data-stu-id="caef0-123">Here are some things to consider when trying to maintain backwards compatibility with older versions of your library:</span></span>

* <span data-ttu-id="caef0-124">Métodos virtuales: cuando hace que un método virtual sea no virtual en su versión nueva, significa que los proyectos que reemplacen ese método tendrán que actualizarse.</span><span class="sxs-lookup"><span data-stu-id="caef0-124">Virtual methods: When you make a virtual method non-virtual in your new version it means that projects that override that method will have to be updated.</span></span> <span data-ttu-id="caef0-125">Esto es un cambio brusco enorme y se desaconseja totalmente.</span><span class="sxs-lookup"><span data-stu-id="caef0-125">This is a huge breaking change and is strongly discouraged.</span></span>
* <span data-ttu-id="caef0-126">Firmas del método: cuando actualizar un comportamiento del método requiere que cambie su firma también, en su lugar, debe crear una sobrecarga de manera que el código que llama a ese método siga funcionando.</span><span class="sxs-lookup"><span data-stu-id="caef0-126">Method signatures: When updating a method behaviour requires you to change its signature as well, you should instead create an overload so that code calling into that method will still work.</span></span>
<span data-ttu-id="caef0-127">Siempre puede manipular la firma del método anterior para llamar a la firma del método nuevo, de manera que la implementación siga siendo coherente.</span><span class="sxs-lookup"><span data-stu-id="caef0-127">You can always manipulate the old method signature to call into the new method signature so that implementation remains consistent.</span></span>
* <span data-ttu-id="caef0-128">[Atributo obsoleto](programming-guide/concepts/attributes/common-attributes.md#Obsolete): puede usar este atributo en su código para especificar clases o miembros de clases que han quedado obsoletos y, que probablemente, se quiten en versiones futuras.</span><span class="sxs-lookup"><span data-stu-id="caef0-128">[Obsolete attribute](programming-guide/concepts/attributes/common-attributes.md#Obsolete): You can use this attribute in your code to specify classes or class members that are deprecated and likely to be removed in future versions.</span></span>
<span data-ttu-id="caef0-129">Esto garantiza que los desarrolladores que usen su biblioteca estén mejor preparados para los cambios bruscos.</span><span class="sxs-lookup"><span data-stu-id="caef0-129">This ensures developers utilizing your library are better prepared for breaking changes.</span></span>
* <span data-ttu-id="caef0-130">Argumentos de método opcionales: cuando hace que los argumentos de método opcionales anteriormente sean obligatorios o cambien su valor predeterminado, entonces todo el código que no proporcione esos argumentos necesitará actualizarse.</span><span class="sxs-lookup"><span data-stu-id="caef0-130">Optional Method Arguments: When you make previously optional method arguments compulsory or change their default value then all code that does not supply those arguments will need to be updated.</span></span>
> [!NOTE]
> <span data-ttu-id="caef0-131">Hacer que los argumentos obligatorios sean opcionales debe tener un efecto muy pequeño, especialmente si no cambia el comportamiento del método.</span><span class="sxs-lookup"><span data-stu-id="caef0-131">Making compulsory arguments optional should have very little effect especially if it doesn't change the method's behaviour.</span></span>

<span data-ttu-id="caef0-132">Cuánto más facilite la actualización a la nueva versión de la biblioteca a sus usuarios, más rápidamente la actualizarán.</span><span class="sxs-lookup"><span data-stu-id="caef0-132">The easier you make it for your users to upgrade to the new version of your library, the more likely that they will upgrade sooner.</span></span>

### <a name="application-configuration-file"></a><span data-ttu-id="caef0-133">Archivo de configuración de aplicación</span><span class="sxs-lookup"><span data-stu-id="caef0-133">Application Configuration File</span></span>

<span data-ttu-id="caef0-134">Como desarrollador de .NET, existe una posibilidad muy alta de que haya encontrado [el archivo `app.config`](https://msdn.microsoft.com/en-us/library/1fk1t1t0(v=vs.110).aspx) en la mayoría de tipos de proyecto.</span><span class="sxs-lookup"><span data-stu-id="caef0-134">As a .NET developer there's a very high chance you've encountered [the `app.config` file](https://msdn.microsoft.com/en-us/library/1fk1t1t0(v=vs.110).aspx) present in most project types.</span></span>
<span data-ttu-id="caef0-135">Este sencillo archivo de configuración puede hacer mucho por mejorar la implementación de las actualizaciones nuevas.</span><span class="sxs-lookup"><span data-stu-id="caef0-135">This simple configuration file can go a long way into improving the rollout of new updates.</span></span> <span data-ttu-id="caef0-136">Generalmente, debe diseñar sus bibliotecas de tal manera que la información que es probable que cambie regularmente se almacene en el archivo `app.config`, de esta manera, cuando dicha información se actualice, el archivo de configuración de las versiones anteriores solo necesita reemplazarse por el nuevo sin necesidad de volver a compilar la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="caef0-136">You should generally design your libraries in such a way that information that is likely to change regularly is stored in the `app.config` file, this way when such information is updated the config file of older versions just needs to be replaced with the new one without the need for recompilation of the library.</span></span>

## <a name="consuming-libraries"></a><span data-ttu-id="caef0-137">Consumo de bibliotecas</span><span class="sxs-lookup"><span data-stu-id="caef0-137">Consuming Libraries</span></span>

<span data-ttu-id="caef0-138">Como desarrollador que consume bibliotecas .NET creadas por otros desarrolladores, es probable que sea consciente de que una nueva versión de una biblioteca puede que no sea completamente compatible con su proyecto y, a menudo, puede que tenga que actualizar su código para trabajar con esos cambios.</span><span class="sxs-lookup"><span data-stu-id="caef0-138">As a developer that consumes .NET libraries built by other developers you're most likely aware that a new version of a library might not be fully compatible with your project and you might often find yourself having to update your code to work with those changes.</span></span>

<span data-ttu-id="caef0-139">Por suerte, C# y el ecosistema de .NET incluyen características y técnicas que nos permiten actualizar fácilmente nuestra aplicación para que funcione con las versiones nuevas de bibliotecas que pueden presentar cambios bruscos.</span><span class="sxs-lookup"><span data-stu-id="caef0-139">Lucky for you C# and the .NET ecosystem comes with features and techniques that allow us to easily update our app to work with new versions of libraries that might introduce breaking changes.</span></span>

### <a name="assembly-binding-redirection"></a><span data-ttu-id="caef0-140">Redirección de enlace de ensamblados</span><span class="sxs-lookup"><span data-stu-id="caef0-140">Assembly Binding Redirection</span></span>

<span data-ttu-id="caef0-141">Puede usar el archivo `app.config` para actualizar la versión de una biblioteca que use su aplicación.</span><span class="sxs-lookup"><span data-stu-id="caef0-141">You can use the `app.config` file to update the version of a library your app uses.</span></span> <span data-ttu-id="caef0-142">Al agregar lo que se denomina una [*redirección de enlace*](https://msdn.microsoft.com/en-us/library/7wd6ex19(v=vs.110).aspx), puede usar la nueva versión de la biblioteca sin tener que volver a compilar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="caef0-142">By adding what is called a [*binding redirect*](https://msdn.microsoft.com/en-us/library/7wd6ex19(v=vs.110).aspx) your can use the new library version without having to recompile your app.</span></span> <span data-ttu-id="caef0-143">En el siguiente ejemplo se muestra cómo actualizaría el archivo `app.config` de la aplicación para usar la versión de revisión `1.0.1` de `ReferencedLibrary`, en lugar de la versión `1.0.0` con la que se ha compilado originalmente.</span><span class="sxs-lookup"><span data-stu-id="caef0-143">The following example shows how you would update your app's `app.config` file to use the `1.0.1` patch version of `ReferencedLibrary` instead of the `1.0.0` version it was originally compiled with.</span></span>

```xml
<dependentAssembly>
    <assemblyIdentity name="ReferencedLibrary" publicKeyToken="32ab4ba45e0a69a1" culture="en-us" />
    <bindingRedirect oldVersion="1.0.0" newVersion="1.0.1" />
</dependentAssembly>
```

> [!NOTE]
> <span data-ttu-id="caef0-144">Este enfoque solo funcionará si la versión nueva de `ReferencedLibrary` tiene compatibilidad binaria con su aplicación.</span><span class="sxs-lookup"><span data-stu-id="caef0-144">This approach will only work if the new version of `ReferencedLibrary` is binary compatible with your app.</span></span>
> <span data-ttu-id="caef0-145">Vea la sección anterior [Compatibilidad con versiones anteriores](#backwards-compatibility) para ver los cambios que debe tener en cuenta al determinar la compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="caef0-145">See the [Backwards Compatibility](#backwards-compatibility) section above for changes to look out for when determining compatibility.</span></span>

### <a name="new"></a><span data-ttu-id="caef0-146">new</span><span class="sxs-lookup"><span data-stu-id="caef0-146">new</span></span>

<span data-ttu-id="caef0-147">Use el modificador `new` para ocultar los miembros heredados de una clase base.</span><span class="sxs-lookup"><span data-stu-id="caef0-147">You use the `new` modifier to hide inherited members of a base class.</span></span> <span data-ttu-id="caef0-148">Esta es una manera en la que las clases derivadas pueden responder a las actualizaciones en clases base.</span><span class="sxs-lookup"><span data-stu-id="caef0-148">This is one way derived classes can respond to updates in base classes.</span></span>

<span data-ttu-id="caef0-149">Considere el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="caef0-149">Take the following example:</span></span>

<span data-ttu-id="caef0-150">[!code-csharp[Uso del ejemplo del modificador "new"](../../samples/csharp/versioning/new/Program.cs#sample)]</span><span class="sxs-lookup"><span data-stu-id="caef0-150">[!code-csharp[Sample usage of the 'new' modifier](../../samples/csharp/versioning/new/Program.cs#sample)]</span></span>

<span data-ttu-id="caef0-151">**Salida**</span><span class="sxs-lookup"><span data-stu-id="caef0-151">**Output**</span></span>

```
A base method
A derived method
```

<span data-ttu-id="caef0-152">En el ejemplo anterior puede ver cómo `DerivedClass` oculta el método `MyMethod` presente en `BaseClass`.</span><span class="sxs-lookup"><span data-stu-id="caef0-152">From the example above you can see how `DerivedClass` hides the `MyMethod` method present in `BaseClass`.</span></span>
<span data-ttu-id="caef0-153">Esto significa que cuando una clase base en la versión nueva de una biblioteca agrega un miembro que ya existe en su clase derivada, simplemente puede usar el modificador `new` en su miembro de clase derivada para ocultar el miembro de clase base.</span><span class="sxs-lookup"><span data-stu-id="caef0-153">This means that when a base class in the new version of a library adds a member that already exists in your derived class, you can simply use the `new` modifier on your derived class member to hide the base class member.</span></span>

<span data-ttu-id="caef0-154">Cuando no se especifica ningún modificador `new`, una clase derivada ocultará de manera predeterminada los miembros en conflicto de una clase base, aunque se generará una advertencia del compilador, el código se compilará.</span><span class="sxs-lookup"><span data-stu-id="caef0-154">When no `new` modifier is specified, a derived class will by default hide conflicting members in a base class, although a compiler warning will be generated the code will still compile.</span></span> <span data-ttu-id="caef0-155">Esto significa que agregar simplemente miembros nuevos a una clase existente, hace que la versión nueva de su biblioteca tenga compatibilidad binaria y de origen con el código que depende de ella.</span><span class="sxs-lookup"><span data-stu-id="caef0-155">This means that simply adding new members to an existing class makes that new version of your library both source and binary compatible with code that depends on it.</span></span>

### <a name="override"></a><span data-ttu-id="caef0-156">override</span><span class="sxs-lookup"><span data-stu-id="caef0-156">override</span></span>

<span data-ttu-id="caef0-157">El modificador `override` significa que una implementación derivada extiende la implementación de un miembro de clase base en lugar de ocultarlo.</span><span class="sxs-lookup"><span data-stu-id="caef0-157">The `override` modifier means a derived implementation extends the implementation of a base class member rather than hides it.</span></span> <span data-ttu-id="caef0-158">El miembro de clase base necesita que se le aplique el modificador `virtual`.</span><span class="sxs-lookup"><span data-stu-id="caef0-158">The base class member needs to have the `virtual` modifier applied to it.</span></span>

<span data-ttu-id="caef0-159">[!code-csharp[Uso del ejemplo del modificador "override"](../../samples/csharp/versioning/override/Program.cs#sample)]</span><span class="sxs-lookup"><span data-stu-id="caef0-159">[!code-csharp[Sample usage of the 'override' modifier](../../samples/csharp/versioning/override/Program.cs#sample)]</span></span>

<span data-ttu-id="caef0-160">**Salida**</span><span class="sxs-lookup"><span data-stu-id="caef0-160">**Output**</span></span>

```
Base Method One: Method One
Derived Method One: Derived Method One
```

<span data-ttu-id="caef0-161">El modificador `override` se evalúa en tiempo de compilación y el compilador producirá un error si no encuentra un miembro virtual que reemplazar.</span><span class="sxs-lookup"><span data-stu-id="caef0-161">The `override` modifier is evaluated at compile time and the compiler will throw an error if it doesn't find a virtual member to override.</span></span>

<span data-ttu-id="caef0-162">Su conocimiento de las técnicas que se han tratado y su comprensión de las situaciones para usarlas harán mucho por mejorar la facilidad de la transición entre las versiones de una biblioteca.</span><span class="sxs-lookup"><span data-stu-id="caef0-162">Your knowledge of the discussed techniques as well as your understanding of what situations to use them will go a long way to boost the ease of transition between versions of a library.</span></span>

