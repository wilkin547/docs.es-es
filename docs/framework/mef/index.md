---
title: Managed Extensibility Framework (MEF)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Managed Extensibility Framework, overview
- MEF, overview
ms.assetid: 6c61b4ec-c6df-4651-80f1-4854f8b14dde
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 323dfe7d68f5a6f6274ce23f82e25a337956b23c
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43386433"
---
# <a name="managed-extensibility-framework-mef"></a><span data-ttu-id="4d080-102">Managed Extensibility Framework (MEF)</span><span class="sxs-lookup"><span data-stu-id="4d080-102">Managed Extensibility Framework (MEF)</span></span>
<span data-ttu-id="4d080-103">En este tema se proporciona información general sobre la biblioteca Managed Extensibility Framework que se incluye en .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="4d080-103">This topic provides an overview of the Managed Extensibility Framework introduced in the .NET Framework 4.</span></span>  
  
<a name="what_is_mef"></a>   
## <a name="what-is-mef"></a><span data-ttu-id="4d080-104">¿Qué es MEF?</span><span class="sxs-lookup"><span data-stu-id="4d080-104">What is MEF?</span></span>  
 <span data-ttu-id="4d080-105">Managed Extensibility Framework o MEF es una biblioteca para crear aplicaciones ligeras y extensibles.</span><span class="sxs-lookup"><span data-stu-id="4d080-105">The Managed Extensibility Framework or MEF is a library for creating lightweight, extensible applications.</span></span> <span data-ttu-id="4d080-106">Permite a los desarrolladores de aplicaciones detectar y utilizar extensiones sin requisitos de configuración.</span><span class="sxs-lookup"><span data-stu-id="4d080-106">It allows application developers to discover and use extensions with no configuration required.</span></span> <span data-ttu-id="4d080-107">También permite a los desarrolladores de extensiones encapsular código con facilidad y evitar dependencias lógicas frágiles.</span><span class="sxs-lookup"><span data-stu-id="4d080-107">It also lets extension developers easily encapsulate code and avoid fragile hard dependencies.</span></span> <span data-ttu-id="4d080-108">MEF no solo permite reutilizar extensiones dentro de las aplicaciones sino también entre aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="4d080-108">MEF not only allows extensions to be reused within applications, but across applications as well.</span></span>  
  
<a name="the_problem_of_extensibility"></a>   
## <a name="the-problem-of-extensibility"></a><span data-ttu-id="4d080-109">El problema de la extensibilidad</span><span class="sxs-lookup"><span data-stu-id="4d080-109">The Problem of Extensibility</span></span>  
 <span data-ttu-id="4d080-110">Imagine que es el arquitecto de una aplicación grande que debe admitir la extensibilidad.</span><span class="sxs-lookup"><span data-stu-id="4d080-110">Imagine that you are the architect of a large application that must provide support for extensibility.</span></span> <span data-ttu-id="4d080-111">Su aplicación tiene que incluir un número potencialmente grande de componentes menores, y es responsable de crearlos y ejecutarlos.</span><span class="sxs-lookup"><span data-stu-id="4d080-111">Your application has to include a potentially large number of smaller components, and is responsible for creating and running them.</span></span>  
  
 <span data-ttu-id="4d080-112">El enfoque más sencillo es incluir los componentes como código fuente en su aplicación y llamarlos directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="4d080-112">The simplest approach to the problem is to include the components as source code in your application, and call them directly from your code.</span></span>  <span data-ttu-id="4d080-113">Esto tiene varias desventajas obvias.</span><span class="sxs-lookup"><span data-stu-id="4d080-113">This has a number of obvious drawbacks.</span></span>  <span data-ttu-id="4d080-114">Mucho más importante es que no puede agregar nuevos componentes sin modificar el código fuente, una restricción que podría ser aceptable en una aplicación web, pero que no es viable en una aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="4d080-114">Most importantly, you cannot add new components without modifying the source code, a restriction that might be acceptable in, for example, a Web application, but is unworkable in a client application.</span></span>  <span data-ttu-id="4d080-115">Igualmente problemático es que podría no tener acceso al código fuente de los componentes, porque tal vez haya sido desarrollado por terceros y, por la misma razón, no puede permitirles acceso al suyo.</span><span class="sxs-lookup"><span data-stu-id="4d080-115">Equally problematic, you may not have access to the source code for the components, because they might be developed by third parties, and for the same reason you cannot allow them to access yours.</span></span>  
  
 <span data-ttu-id="4d080-116">Un enfoque ligeramente más sofisticado sería proporcionar un punto de extensión o interfaz para permitir la desasociación entre la aplicación y sus componentes.</span><span class="sxs-lookup"><span data-stu-id="4d080-116">A slightly more sophisticated approach would be to provide an extension point or interface, to permit decoupling between the application and its components.</span></span>  <span data-ttu-id="4d080-117">Con este modelo, podría proporcionar una interfaz que un componente pueda implementar, y una API para que pueda interactuar con su aplicación.</span><span class="sxs-lookup"><span data-stu-id="4d080-117">Under this model, you might provide an interface that a component can implement, and an API to enable it to interact with your application.</span></span>  <span data-ttu-id="4d080-118">Así se resuelve el problema del acceso al código fuente, pero todavía presenta dificultades.</span><span class="sxs-lookup"><span data-stu-id="4d080-118">This solves the problem of requiring source code access, but it still has its own difficulties.</span></span>  
  
 <span data-ttu-id="4d080-119">Dado que a la aplicación le falta la capacidad para detectar los componentes por sí misma, se debe indicar explícitamente qué componentes están disponibles y deben cargarse.</span><span class="sxs-lookup"><span data-stu-id="4d080-119">Because the application lacks any capacity for discovering components on its own, it must still be explicitly told which components are available and should be loaded.</span></span>  <span data-ttu-id="4d080-120">Por lo general, esto se logra registrando explícitamente los componentes disponibles en un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="4d080-120">This is typically accomplished by explicitly registering the available components in a configuration file.</span></span> <span data-ttu-id="4d080-121">Esto significa que asegurar que los componentes sean correctos se convierte en una cuestión de mantenimiento, especialmente si usted es el usuario final y no el desarrollador que se espera que haga la actualización.</span><span class="sxs-lookup"><span data-stu-id="4d080-121">This means that assuring that the components are correct becomes a maintenance issue, particularly if it is the end user and not the developer who is expected to do the updating.</span></span>  
  
 <span data-ttu-id="4d080-122">Además, los componentes no pueden comunicarse entre sí, excepto a través de los canales estrictamente definidos en el código de la propia aplicación.</span><span class="sxs-lookup"><span data-stu-id="4d080-122">In addition, components are incapable of communicating with one another, except through the rigidly defined channels of the application itself.</span></span>  <span data-ttu-id="4d080-123">Si el arquitecto de la aplicación no ha previsto la necesidad de una comunicación determinada, normalmente es imposible.</span><span class="sxs-lookup"><span data-stu-id="4d080-123">If the application architect has not anticipated the need for a particular communication, it is usually impossible.</span></span>  
  
 <span data-ttu-id="4d080-124">Por último, los desarrolladores de componentes deben aceptar una dependencia fuerte en el ensamblado que contiene la interfaz que implementan.</span><span class="sxs-lookup"><span data-stu-id="4d080-124">Finally, the component developers must accept a hard dependency on what assembly contains the interface they implement.</span></span>  <span data-ttu-id="4d080-125">Esto dificulta que un componente se use en más de una aplicación y también puede crear problemas cuando se crea un marco de pruebas para los componentes.</span><span class="sxs-lookup"><span data-stu-id="4d080-125">This makes it difficult for a component to be used in more than one application, and can also create problems when you create a test framework for components.</span></span>  
  
<a name="what_mef_provides"></a>   
## <a name="what-mef-provides"></a><span data-ttu-id="4d080-126">Qué proporciona MEF</span><span class="sxs-lookup"><span data-stu-id="4d080-126">What MEF Provides</span></span>  
 <span data-ttu-id="4d080-127">En lugar de este registro explícito de componentes disponibles, MEF proporciona una manera de detectarlos implícitamente, a través de la *composición*.</span><span class="sxs-lookup"><span data-stu-id="4d080-127">Instead of this explicit registration of available components, MEF provides a way to discover them implicitly, via *composition*.</span></span>  <span data-ttu-id="4d080-128">Un componente MEF, denominado *elemento*, especifica mediante declaración tanto sus dependencias (conocidas como *importaciones*) como qué funcionalidades (conocidas como *exportaciones*) están disponibles.</span><span class="sxs-lookup"><span data-stu-id="4d080-128">A MEF component, called a *part*, declaratively specifies both its dependencies (known as *imports*) and what capabilities (known as *exports*) it makes available.</span></span> <span data-ttu-id="4d080-129">Cuando se crea un elemento, el motor de composición de MEF cubre sus importaciones con lo que está disponible en otros elementos</span><span class="sxs-lookup"><span data-stu-id="4d080-129">When a part is created, the MEF composition engine satisfies its imports with what is available from other parts.</span></span>  
  
 <span data-ttu-id="4d080-130">Este enfoque resuelve los problemas comentados en la sección anterior.</span><span class="sxs-lookup"><span data-stu-id="4d080-130">This approach solves the problems discussed in the previous section.</span></span>  <span data-ttu-id="4d080-131">Dado que los elementos MEF especifican sus capacidades mediante declaración, son reconocibles en tiempo de ejecución, lo que significa que una aplicación puede utilizar elementos sin referencias incluidas en el código o archivos de configuración frágiles.</span><span class="sxs-lookup"><span data-stu-id="4d080-131">Because MEF parts declaratively specify their capabilities, they are discoverable at runtime, which means an application can make use of parts without either hard-coded references or fragile configuration files.</span></span>  <span data-ttu-id="4d080-132">MEF permite a las aplicaciones detectar y examinar elementos por sus metadatos, sin crear instancias ni cargar sus ensamblados.</span><span class="sxs-lookup"><span data-stu-id="4d080-132">MEF allows applications to discover and examine parts by their metadata, without instantiating them or even loading their assemblies.</span></span> <span data-ttu-id="4d080-133">Por consiguiente, no hay necesidad de especificar meticulosamente qué extensiones se deben cargar y cuándo.</span><span class="sxs-lookup"><span data-stu-id="4d080-133">As a result, there is no need to carefully specify when and how extensions should be loaded.</span></span>  
  
 <span data-ttu-id="4d080-134">Además de las exportaciones proporcionadas, un elemento puede especificar las importaciones, que serán completadas por otros elementos.</span><span class="sxs-lookup"><span data-stu-id="4d080-134">In addition to its provided exports, a part can specify its imports, which will be filled by other parts.</span></span>  <span data-ttu-id="4d080-135">Esto hace que la comunicación entre los elementos sea posible además de sencilla y permite una buena factorización del código.</span><span class="sxs-lookup"><span data-stu-id="4d080-135">This makes communication among parts not only possible, but easy, and allows for good factoring of code.</span></span> <span data-ttu-id="4d080-136">Por ejemplo, los servicios comunes a muchos componentes se pueden tener en cuenta en un elemento independiente, para modificarlos o reemplazarlos con facilidad.</span><span class="sxs-lookup"><span data-stu-id="4d080-136">For example, services common to many components can be factored into a separate part and easily modified or replaced.</span></span>  
  
 <span data-ttu-id="4d080-137">Dado que el modelo MEF no requiere dependencias lógicas en un ensamblado de aplicación determinado, permite reutilizar las extensiones entre una aplicación y otra.</span><span class="sxs-lookup"><span data-stu-id="4d080-137">Because the MEF model requires no hard dependency on a particular application assembly, it allows extensions to be reused from application to application.</span></span>  <span data-ttu-id="4d080-138">Esto también facilita el desarrollo de un agente de prueba, independiente de la aplicación, para probar los componentes de extensión.</span><span class="sxs-lookup"><span data-stu-id="4d080-138">This also makes it easy to develop a test harness, independent of the application, to test extension components.</span></span>  
  
 <span data-ttu-id="4d080-139">Una aplicación extensible escrita utilizando MEF declara una importación que puede ser completada por componentes de extensión y también puede declarar exportaciones para exponer servicios de aplicación a extensiones.</span><span class="sxs-lookup"><span data-stu-id="4d080-139">An extensible application written by using MEF declares an import that can be filled by extension components, and may also declare exports in order to expose application services to extensions.</span></span>  <span data-ttu-id="4d080-140">Cada componente de extensión declara una exportación y también puede declarar importaciones.</span><span class="sxs-lookup"><span data-stu-id="4d080-140">Each extension component declares an export, and may also declare imports.</span></span>  <span data-ttu-id="4d080-141">De esta manera, los componentes de extensión son automáticamente extensibles.</span><span class="sxs-lookup"><span data-stu-id="4d080-141">In this way, extension components themselves are automatically extensible.</span></span>  
  
<a name="where_is_mef_available"></a>   
## <a name="where-is-mef-available"></a><span data-ttu-id="4d080-142">¿Dónde está MEF disponible?</span><span class="sxs-lookup"><span data-stu-id="4d080-142">Where Is MEF Available?</span></span>  
 <span data-ttu-id="4d080-143">MEF es una parte integral de [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] y está disponible dondequiera que se use .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4d080-143">MEF is an integral part of the [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], and is available wherever the .NET Framework is used.</span></span>  <span data-ttu-id="4d080-144">Puede utilizar MEF en aplicaciones cliente, que usen Windows Forms, WPF o cualquier otra tecnología, o en aplicaciones servidor que usen ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="4d080-144">You can use MEF in your client applications, whether they use Windows Forms, WPF, or any other technology, or in server applications that use ASP.NET.</span></span>  
  
<a name="mef_and_maf"></a>   
## <a name="mef-and-maf"></a><span data-ttu-id="4d080-145">MEF y MAF</span><span class="sxs-lookup"><span data-stu-id="4d080-145">MEF and MAF</span></span>  
 <span data-ttu-id="4d080-146">En versiones anteriores de .NET Framework se presentó Managed Add-in Framework (MAF), diseñado para permitir a las aplicaciones aislar y administrar extensiones.</span><span class="sxs-lookup"><span data-stu-id="4d080-146">Previous versions of the .NET Framework introduced the Managed Add-in Framework (MAF), designed to allow applications to isolate and manage extensions.</span></span>  <span data-ttu-id="4d080-147">MAF se centra en un nivel ligeramente más alto que MEF y se concentra en el aislamiento de la extensión y la carga y descarga del ensamblado, mientras que MEF se centra en la detectabilidad, extensibilidad y portabilidad.</span><span class="sxs-lookup"><span data-stu-id="4d080-147">The focus of MAF is slightly higher-level than MEF, concentrating on extension isolation and assembly loading and unloading, while MEF's focus is on discoverability, extensibility, and portability.</span></span>  <span data-ttu-id="4d080-148">Los dos marcos interoperan fácilmente y una aplicación única puede aprovecharse de ambos.</span><span class="sxs-lookup"><span data-stu-id="4d080-148">The two frameworks interoperate smoothly, and a single application can take advantage of both.</span></span>  
  
<a name="simplecalculator_an_example_application"></a>   
## <a name="simplecalculator-an-example-application"></a><span data-ttu-id="4d080-149">SimpleCalculator: aplicación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="4d080-149">SimpleCalculator: An Example Application</span></span>  
 <span data-ttu-id="4d080-150">La manera más sencilla de ver qué puede hacer MEF es compilar una aplicación sencilla con él.</span><span class="sxs-lookup"><span data-stu-id="4d080-150">The simplest way to see what MEF can do is to build a simple MEF application.</span></span> <span data-ttu-id="4d080-151">En este ejemplo, compilará una calculadora muy sencilla denominada SimpleCalculator.</span><span class="sxs-lookup"><span data-stu-id="4d080-151">In this example, you build a very simple calculator named SimpleCalculator.</span></span> <span data-ttu-id="4d080-152">El objetivo de SimpleCalculator es crear una aplicación de consola que acepte comandos aritméticos básicos, con el formato "5+3" ó "6-2", y devuelva respuestas correctas.</span><span class="sxs-lookup"><span data-stu-id="4d080-152">The goal of SimpleCalculator is to create a console application that accepts basic arithmetic commands, in the form "5+3" or "6-2", and returns the correct answers.</span></span> <span data-ttu-id="4d080-153">Con MEF, podrá agregar nuevos operadores sin cambiar el código de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4d080-153">Using MEF, you will be able to add new operators without changing the application code.</span></span>  
  
 <span data-ttu-id="4d080-154">Para descargar el código completo de este ejemplo, consulte [Ejemplo SimpleCalculator](https://code.msdn.microsoft.com/windowsdesktop/Simple-Calculator-MEF-1152654e).</span><span class="sxs-lookup"><span data-stu-id="4d080-154">To download the complete code for this example, see the [SimpleCalculator sample](https://code.msdn.microsoft.com/windowsdesktop/Simple-Calculator-MEF-1152654e).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4d080-155">La finalidad de SimpleCalculator es mostrar los conceptos y la sintaxis de MEF, más que proporcionar un escenario realista para su uso.</span><span class="sxs-lookup"><span data-stu-id="4d080-155">The purpose of SimpleCalculator is to demonstrate the concepts and syntax of MEF, rather than to necessarily provide a realistic scenario for its use.</span></span> <span data-ttu-id="4d080-156">Muchas de las aplicaciones que más se beneficiarían de todo lo que MEF puede ofrecer son más complejas que SimpleCalculator.</span><span class="sxs-lookup"><span data-stu-id="4d080-156">Many of the applications that would benefit most from the power of MEF are more complex than SimpleCalculator.</span></span> <span data-ttu-id="4d080-157">Para obtener ejemplos más exhaustivos, consulte [Managed Extensibility Framework](https://github.com/MicrosoftArchive/mef) en GitHub.</span><span class="sxs-lookup"><span data-stu-id="4d080-157">For more extensive examples, see the [Managed Extensibility Framework](https://github.com/MicrosoftArchive/mef) on GitHub.</span></span>
  
 <span data-ttu-id="4d080-158">Para empezar, en [!INCLUDE[vs_dev10_long](../../../includes/vs-dev10-long-md.md)], cree un nuevo proyecto de Aplicación de consola denominado `SimpleCalculator`.</span><span class="sxs-lookup"><span data-stu-id="4d080-158">To start, in [!INCLUDE[vs_dev10_long](../../../includes/vs-dev10-long-md.md)], create a new Console Application project named `SimpleCalculator`.</span></span> <span data-ttu-id="4d080-159">Agregue una referencia al ensamblado System.ComponentModel.Composition, donde reside MEF.</span><span class="sxs-lookup"><span data-stu-id="4d080-159">Add a reference to the System.ComponentModel.Composition assembly, where MEF resides.</span></span> <span data-ttu-id="4d080-160">Abra Module1.vb o Program.cs y agregue instrucciones `Imports` o `using` para System.ComponentModel.Composition y System.ComponentModel.Composition.Hosting.</span><span class="sxs-lookup"><span data-stu-id="4d080-160">Open Module1.vb or Program.cs and add `Imports` or `using` statements for System.ComponentModel.Composition and System.ComponentModel.Composition.Hosting.</span></span> <span data-ttu-id="4d080-161">Estos dos espacios de nombres contienen tipos MEF que necesitará para desarrollar una aplicación extensible.</span><span class="sxs-lookup"><span data-stu-id="4d080-161">These two namespaces contain MEF types you will need to develop an extensible application.</span></span> <span data-ttu-id="4d080-162">En Visual Basic, agregue la palabra clave `Public` a la línea que declara el módulo `Module1`.</span><span class="sxs-lookup"><span data-stu-id="4d080-162">In Visual Basic, add the `Public` keyword to the line that declares the `Module1` module.</span></span>  
  
<a name="composition_container_and_catalogs"></a>   
## <a name="composition-container-and-catalogs"></a><span data-ttu-id="4d080-163">Contenedor de composición y catálogos</span><span class="sxs-lookup"><span data-stu-id="4d080-163">Composition Container and Catalogs</span></span>  
 <span data-ttu-id="4d080-164">El núcleo del modelo de composición de MEF es el *contenedor de composición*, que contiene todos los elementos disponibles y realiza la composición.</span><span class="sxs-lookup"><span data-stu-id="4d080-164">The core of the MEF composition model is the *composition container*, which contains all the parts available and performs composition.</span></span>  <span data-ttu-id="4d080-165">(Es decir, la concordancia de importaciones y exportaciones).  El tipo más común de contenedor de composición es <xref:System.ComponentModel.Composition.Hosting.CompositionContainer> y lo utilizará en SimpleCalculator.</span><span class="sxs-lookup"><span data-stu-id="4d080-165">(That is, the matching up of imports to exports.)  The most common type of composition container is <xref:System.ComponentModel.Composition.Hosting.CompositionContainer>, and you will use this for SimpleCalculator.</span></span>  
  
 <span data-ttu-id="4d080-166">En Visual Basic, en Module1.vb, agregue una clase pública denominada `Program`.</span><span class="sxs-lookup"><span data-stu-id="4d080-166">In Visual Basic, in Module1.vb, add a public class named `Program`.</span></span> <span data-ttu-id="4d080-167">A continuación, agregue la línea siguiente a la clase `Program` en Module1.vb o Program.cs:</span><span class="sxs-lookup"><span data-stu-id="4d080-167">Then add the following line to the `Program` class in Module1.vb or Program.cs:</span></span>  
  
```vb  
Dim _container As CompositionContainer  
```  
  
```csharp  
private CompositionContainer _container;  
```  
  
 <span data-ttu-id="4d080-168">Para detectar los elementos disponibles, el contenedor de composición hace uso de un *catálogo*.</span><span class="sxs-lookup"><span data-stu-id="4d080-168">In order to discover the parts available to it, the composition containers makes use of a *catalog*.</span></span> <span data-ttu-id="4d080-169">Un catálogo es un objeto que hace que los elementos disponibles se detecten en algún origen.</span><span class="sxs-lookup"><span data-stu-id="4d080-169">A catalog is an object that makes available parts discovered from some source.</span></span>  <span data-ttu-id="4d080-170">MEF proporciona catálogos para detectar las partes de un tipo, un ensamblado o un directorio suministrado.</span><span class="sxs-lookup"><span data-stu-id="4d080-170">MEF provides catalogs to discover parts from a provided type, an assembly, or a directory.</span></span> <span data-ttu-id="4d080-171">Los desarrolladores de aplicaciones pueden crear fácilmente nuevos catálogos para detectar partes de otros orígenes, como un servicio Web.</span><span class="sxs-lookup"><span data-stu-id="4d080-171">Application developers can easily create new catalogs to discover parts from other sources, such as a Web service.</span></span>  
  
 <span data-ttu-id="4d080-172">Agregue el siguiente constructor a la clase `Program`:</span><span class="sxs-lookup"><span data-stu-id="4d080-172">Add the following constructor to the `Program` class:</span></span>  
  
```vb  
Public Sub New()  
    'An aggregate catalog that combines multiple catalogs  
     Dim catalog = New AggregateCatalog()  
  
    'Adds all the parts found in the same assembly as the Program class  
    catalog.Catalogs.Add(New AssemblyCatalog(GetType(Program).Assembly))  
  
    'Create the CompositionContainer with the parts in the catalog  
    _container = New CompositionContainer(catalog)  
  
    'Fill the imports of this object  
    Try  
        _container.ComposeParts(Me)  
    Catch ex As Exception  
        Console.WriteLine(ex.ToString)  
    End Try  
End Sub  
```  
  
```csharp  
private Program()  
{  
    //An aggregate catalog that combines multiple catalogs  
    var catalog = new AggregateCatalog();  
    //Adds all the parts found in the same assembly as the Program class  
    catalog.Catalogs.Add(new AssemblyCatalog(typeof(Program).Assembly));  
  
    //Create the CompositionContainer with the parts in the catalog  
    _container = new CompositionContainer(catalog);  
  
    //Fill the imports of this object  
    try  
    {  
        this._container.ComposeParts(this);  
    }  
    catch (CompositionException compositionException)  
    {  
        Console.WriteLine(compositionException.ToString());  
   }  
}  
```  
  
 <span data-ttu-id="4d080-173">La llamada a <xref:System.ComponentModel.Composition.AttributedModelServices.ComposeParts%2A> indica al contenedor de composición que cree un conjunto específico de elementos, en este caso la instancia actual de `Program`.</span><span class="sxs-lookup"><span data-stu-id="4d080-173">The call to <xref:System.ComponentModel.Composition.AttributedModelServices.ComposeParts%2A> tells the composition container to compose a specific set of parts, in this case the current instance of `Program`.</span></span> <span data-ttu-id="4d080-174">En este punto, sin embargo, no sucederá nada, dado que `Program` no tiene importaciones que completar.</span><span class="sxs-lookup"><span data-stu-id="4d080-174">At this point, however, nothing will happen, since `Program` has no imports to fill.</span></span>  
  
<a name="imports_and_exports_with_attributes"></a>   
## <a name="imports-and-exports-with-attributes"></a><span data-ttu-id="4d080-175">Importaciones y exportaciones con atributos</span><span class="sxs-lookup"><span data-stu-id="4d080-175">Imports and Exports with Attributes</span></span>  
 <span data-ttu-id="4d080-176">Primeramente, haga que `Program` importe una calculadora.</span><span class="sxs-lookup"><span data-stu-id="4d080-176">First, you have `Program` import a calculator.</span></span> <span data-ttu-id="4d080-177">Esto permite la separación de los problemas de la interfaz de usuario, como la entrada y salida de consola que irá a `Program`, de la lógica de la calculadora.</span><span class="sxs-lookup"><span data-stu-id="4d080-177">This allows the separation of user interface concerns, such as the console input and output that will go into `Program`, from the logic of the calculator.</span></span>  
  
 <span data-ttu-id="4d080-178">Agregue el código siguiente a la clase `Program` :</span><span class="sxs-lookup"><span data-stu-id="4d080-178">Add the following code to the `Program` class:</span></span>  
  
```vb  
<Import(GetType(ICalculator))>  
Public Property calculator As ICalculator  
```  
  
```csharp  
[Import(typeof(ICalculator))]  
public ICalculator calculator;  
```  
  
 <span data-ttu-id="4d080-179">Observe que la declaración del objeto `calculator` no es rara, pero se decora con el atributo <xref:System.ComponentModel.Composition.ImportAttribute>.</span><span class="sxs-lookup"><span data-stu-id="4d080-179">Notice that the declaration of the `calculator` object is not unusual, but that it is decorated with the <xref:System.ComponentModel.Composition.ImportAttribute> attribute.</span></span>  <span data-ttu-id="4d080-180">Este atributo declara que algo es una importación, es decir, el motor de la composición la completará cuando se cree el objeto.</span><span class="sxs-lookup"><span data-stu-id="4d080-180">This attribute declares something to be an import; that is, it will be filled by the composition engine when the object is composed.</span></span>  
  
 <span data-ttu-id="4d080-181">Cada importación tiene un *contrato* que determina con qué exportaciones coincidirá.</span><span class="sxs-lookup"><span data-stu-id="4d080-181">Every import has a *contract*, which determines what exports it will be matched with.</span></span> <span data-ttu-id="4d080-182">El contrato puede ser una cadena especificada explícitamente o MEF puede generarla automáticamente a partir de un tipo determinado, en este caso la interfaz `ICalculator`.</span><span class="sxs-lookup"><span data-stu-id="4d080-182">The contract can be an explicitly specified string, or it can be automatically generated by MEF from a given type, in this case the interface `ICalculator`.</span></span>  <span data-ttu-id="4d080-183">Cualquier exportación declarada con un contrato coincidente completará esta importación.</span><span class="sxs-lookup"><span data-stu-id="4d080-183">Any export declared with a matching contract will fulfill this import.</span></span>  <span data-ttu-id="4d080-184">Tenga en cuenta que mientras el tipo del objeto `calculator` sea de hecho `ICalculator`, esto no es necesario.</span><span class="sxs-lookup"><span data-stu-id="4d080-184">Note that while the type of the `calculator` object is in fact `ICalculator`, this is not required.</span></span> <span data-ttu-id="4d080-185">El contrato es independiente del tipo del objeto de importación.</span><span class="sxs-lookup"><span data-stu-id="4d080-185">The contract is independent from the type of the importing object.</span></span>  <span data-ttu-id="4d080-186">(En este caso, podría omitir `typeof(ICalculator)`.</span><span class="sxs-lookup"><span data-stu-id="4d080-186">(In this case, you could leave out the `typeof(ICalculator)`.</span></span>  <span data-ttu-id="4d080-187">MEF adoptará automáticamente el contrato que se va a basar en el tipo de importación, a menos que lo especifique explícitamente).</span><span class="sxs-lookup"><span data-stu-id="4d080-187">MEF will automatically assume the contract to be based on the type of the import unless you specify it explicitly.)</span></span>  
  
 <span data-ttu-id="4d080-188">Agregue esta sencilla interfaz al módulo o al espacio de nombres `SimpleCalculator`:</span><span class="sxs-lookup"><span data-stu-id="4d080-188">Add this very simple interface to the module or `SimpleCalculator` namespace:</span></span>  
  
```vb  
Public Interface ICalculator  
    Function Calculate(ByVal input As String) As String  
End Interface  
```  
  
```csharp  
public interface ICalculator  
{  
    String Calculate(String input);  
}  
```  
  
 <span data-ttu-id="4d080-189">Ahora que ha definido `ICalculator`, necesita una clase que lo implemente.</span><span class="sxs-lookup"><span data-stu-id="4d080-189">Now that you have defined `ICalculator`, you need a class that implements it.</span></span>  <span data-ttu-id="4d080-190">Agregue la siguiente clase al módulo o al espacio de nombres `SimpleCalculator`:</span><span class="sxs-lookup"><span data-stu-id="4d080-190">Add the following class to the module or `SimpleCalculator` namespace:</span></span>  
  
```vb  
<Export(GetType(ICalculator))>  
Public Class MySimpleCalculator  
   Implements ICalculator  
  
End Class  
```  
  
```csharp  
[Export(typeof(ICalculator))]  
class MySimpleCalculator : ICalculator  
{  
  
}  
```  
  
 <span data-ttu-id="4d080-191">Aquí está la exportación que coincidirá con la importación en `Program`.</span><span class="sxs-lookup"><span data-stu-id="4d080-191">Here is the export that will match the import in `Program`.</span></span> <span data-ttu-id="4d080-192">Para que la exportación coincida con la importación, la exportación debe tener el mismo contrato.</span><span class="sxs-lookup"><span data-stu-id="4d080-192">In order for the export to match the import, the export must have the same contract.</span></span>  <span data-ttu-id="4d080-193">La exportación bajo un contrato basado en `typeof(MySimpleCalculator)` generará una desigualdad y no se completará la importación; el contrato debe coincidir exactamente.</span><span class="sxs-lookup"><span data-stu-id="4d080-193">Exporting under a contract based on `typeof(MySimpleCalculator)` would produce a mismatch, and the import would not be filled; the contract needs to match exactly.</span></span>  
  
 <span data-ttu-id="4d080-194">Puesto que el contenedor de composición se rellenará con todos los elementos disponibles de este ensamblado, el elemento `MySimpleCalculator` estará disponible.</span><span class="sxs-lookup"><span data-stu-id="4d080-194">Since the composition container will be populated with all the parts available in this assembly, the `MySimpleCalculator` part will be available.</span></span>  <span data-ttu-id="4d080-195">Cuando el constructor `Program` realiza la composición en el objeto `Program`, su importación se completará con un objeto `MySimpleCalculator`, que se creará con ese fin.</span><span class="sxs-lookup"><span data-stu-id="4d080-195">When the constructor for `Program` performs composition on the `Program` object, its import will be filled with a `MySimpleCalculator` object, which will be created for that purpose.</span></span>  
  
 <span data-ttu-id="4d080-196">La capa de interfaz de usuario (`Program`) no necesita más información.</span><span class="sxs-lookup"><span data-stu-id="4d080-196">The user interface layer (`Program`) does not need to know anything else.</span></span>  <span data-ttu-id="4d080-197">Por tanto, puede rellenar el resto de la lógica de la interfaz de usuario en el método `Main`.</span><span class="sxs-lookup"><span data-stu-id="4d080-197">You can therefore fill in the rest of the user interface logic in the `Main` method.</span></span>  
  
 <span data-ttu-id="4d080-198">Agregue el código siguiente al método `Main`:</span><span class="sxs-lookup"><span data-stu-id="4d080-198">Add the following code to the `Main` method:</span></span>  
  
```vb  
Sub Main()  
    Dim p As New Program()  
    Dim s As String  
    Console.WriteLine("Enter Command:")  
    While (True)  
        s = Console.ReadLine()  
        Console.WriteLine(p.calculator.Calculate(s))  
    End While  
End Sub  
```  
  
```csharp  
static void Main(string[] args)  
{  
    Program p = new Program(); //Composition is performed in the constructor  
    String s;  
    Console.WriteLine("Enter Command:");  
    while (true)  
    {  
        s = Console.ReadLine();  
        Console.WriteLine(p.calculator.Calculate(s));  
    }  
}  
```  
  
 <span data-ttu-id="4d080-199">Este código simplemente lee una línea de entrada y llama a la función `Calculate` de `ICalculator` en el resultado, que lo vuelve a escribir en la consola.</span><span class="sxs-lookup"><span data-stu-id="4d080-199">This code simply reads a line of input and calls the `Calculate` function of `ICalculator` on the result, which it writes back to the console.</span></span> <span data-ttu-id="4d080-200">Ese es todo el código que necesita en `Program`.</span><span class="sxs-lookup"><span data-stu-id="4d080-200">That is all the code you need in `Program`.</span></span>  <span data-ttu-id="4d080-201">El resto del trabajo se hará en los elementos.</span><span class="sxs-lookup"><span data-stu-id="4d080-201">All the rest of the work will happen in the parts.</span></span>  
  
<a name="further_imports_and_importmany"></a>   
## <a name="further-imports-and-importmany"></a><span data-ttu-id="4d080-202">Más importaciones e ImportMany</span><span class="sxs-lookup"><span data-stu-id="4d080-202">Further Imports and ImportMany</span></span>  
 <span data-ttu-id="4d080-203">Para que SimpleCalculator sea extensible, necesita importar una lista de operaciones.</span><span class="sxs-lookup"><span data-stu-id="4d080-203">In order for SimpleCalculator to be extensible, it needs to import a list of operations.</span></span> <span data-ttu-id="4d080-204">Un atributo <xref:System.ComponentModel.Composition.ImportAttribute> lo completa un atributo <xref:System.ComponentModel.Composition.ExportAttribute> y solo uno.</span><span class="sxs-lookup"><span data-stu-id="4d080-204">An ordinary <xref:System.ComponentModel.Composition.ImportAttribute> attribute is filled by one and only one <xref:System.ComponentModel.Composition.ExportAttribute>.</span></span>  <span data-ttu-id="4d080-205">Si hay más de uno disponible, el motor de la composición genera un error.</span><span class="sxs-lookup"><span data-stu-id="4d080-205">If more than one is available, the composition engine produces an error.</span></span>  <span data-ttu-id="4d080-206">Para crear una importación que pueda ser completada por cualquier número de exportaciones, puede usar el atributo <xref:System.ComponentModel.Composition.ImportManyAttribute>.</span><span class="sxs-lookup"><span data-stu-id="4d080-206">To create an import that can be filled by any number of exports, you can use the <xref:System.ComponentModel.Composition.ImportManyAttribute> attribute.</span></span>  
  
 <span data-ttu-id="4d080-207">Agregue la siguiente propiedad de operaciones a la clase `MySimpleCalculator`:</span><span class="sxs-lookup"><span data-stu-id="4d080-207">Add the following operations property to the `MySimpleCalculator` class:</span></span>  
  
```vb  
<ImportMany()>  
Public Property operations As IEnumerable(Of Lazy(Of IOperation, IOperationData))  
```  
  
```csharp  
[ImportMany]  
IEnumerable<Lazy<IOperation, IOperationData>> operations;  
```  
  
 <span data-ttu-id="4d080-208"><xref:System.Lazy%602> es un tipo de colección proporcionado por MEF que contiene referencias indirectas a las exportaciones.</span><span class="sxs-lookup"><span data-stu-id="4d080-208"><xref:System.Lazy%602> is a type provided by MEF to hold indirect references to exports.</span></span>  <span data-ttu-id="4d080-209">Aquí, además del propio objeto exportado, también obtiene los *metadatos de la exportación* o información que describe el objeto exportado.</span><span class="sxs-lookup"><span data-stu-id="4d080-209">Here, in addition to the exported object itself, you also get *export metadata*, or information that describes the exported object.</span></span> <span data-ttu-id="4d080-210">Cada colección <xref:System.Lazy%602> contiene un objeto `IOperation`, que representa una operación real, y un objeto `IOperationData`, que representa sus metadatos.</span><span class="sxs-lookup"><span data-stu-id="4d080-210">Each <xref:System.Lazy%602> contains an `IOperation` object, representing an actual operation, and an `IOperationData` object, representing its metadata.</span></span>  
  
 <span data-ttu-id="4d080-211">Agregue estas sencillas interfaces al módulo o al espacio de nombres `SimpleCalculator`:</span><span class="sxs-lookup"><span data-stu-id="4d080-211">Add the following simple interfaces to the module or `SimpleCalculator` namespace:</span></span>  
  
```vb  
Public Interface IOperation  
    Function Operate(ByVal left As Integer, ByVal right As Integer) As Integer  
End Interface  
  
Public Interface IOperationData  
    ReadOnly Property Symbol As Char  
End Interface  
```  
  
```csharp  
public interface IOperation  
{  
     int Operate(int left, int right);  
}  
  
public interface IOperationData  
{  
    Char Symbol { get; }  
}  
```  
  
 <span data-ttu-id="4d080-212">En este caso, los metadatos de cada operación son el símbolo que representa esa operación, como +, -, \*, etc.</span><span class="sxs-lookup"><span data-stu-id="4d080-212">In this case, the metadata for each operation is the symbol that represents that operation, such as +, -, \*, and so on.</span></span> <span data-ttu-id="4d080-213">Para que la operación de suma esté disponible, agregue la siguiente clase al módulo o al espacio de nombres `SimpleCalculator`:</span><span class="sxs-lookup"><span data-stu-id="4d080-213">To make the addition operation available, add the following class to the module or `SimpleCalculator` namespace:</span></span>  
  
```vb  
<Export(GetType(IOperation))>  
<ExportMetadata("Symbol", "+"c)>  
Public Class Add  
    Implements IOperation  
  
    Public Function Operate(ByVal left As Integer, ByVal right As Integer) As Integer Implements IOperation.Operate  
        Return left + right  
    End Function  
End Class  
```  
  
```csharp  
[Export(typeof(IOperation))]  
[ExportMetadata("Symbol", '+')]  
class Add: IOperation  
{  
    public int Operate(int left, int right)  
    {  
        return left + right;  
    }  
}  
```  
  
 <span data-ttu-id="4d080-214">El atributo <xref:System.ComponentModel.Composition.ExportAttribute> funciona igual que antes.</span><span class="sxs-lookup"><span data-stu-id="4d080-214">The <xref:System.ComponentModel.Composition.ExportAttribute> attribute functions as it did before.</span></span>  <span data-ttu-id="4d080-215">El atributo <xref:System.ComponentModel.Composition.ExportMetadataAttribute> adjunta metadatos, con formato de un par nombre-valor, a esa exportación.</span><span class="sxs-lookup"><span data-stu-id="4d080-215">The <xref:System.ComponentModel.Composition.ExportMetadataAttribute> attribute attaches metadata, in the form of a name-value pair, to that export.</span></span>  <span data-ttu-id="4d080-216">Mientras que la clase `Add` implementa `IOperation`, no se define explícitamente una clase que implementa `IOperationData`.</span><span class="sxs-lookup"><span data-stu-id="4d080-216">While the `Add` class implements `IOperation`, a class that implements `IOperationData` is not explicitly defined.</span></span> <span data-ttu-id="4d080-217">En su lugar, MEF crea implícitamente una clase con propiedades basadas en los nombres de los metadatos proporcionados.</span><span class="sxs-lookup"><span data-stu-id="4d080-217">Instead, a class is implicitly created by MEF with properties based on the names of the metadata provided.</span></span>  <span data-ttu-id="4d080-218">(Esta es una de las maneras de tener acceso a los metadatos en MEF).</span><span class="sxs-lookup"><span data-stu-id="4d080-218">(This is one of several ways to access metadata in MEF.)</span></span>  
  
 <span data-ttu-id="4d080-219">La composición en MEF es *recursiva*.</span><span class="sxs-lookup"><span data-stu-id="4d080-219">Composition in MEF is *recursive*.</span></span> <span data-ttu-id="4d080-220">Compuso el objeto `Program` explícitamente, que importó un `ICalculator` que resultó de ser del tipo `MySimpleCalculator`.</span><span class="sxs-lookup"><span data-stu-id="4d080-220">You explicitly composed the `Program` object, which imported an `ICalculator` that turned out to be of type `MySimpleCalculator`.</span></span>  <span data-ttu-id="4d080-221">A su vez, `MySimpleCalculator` importa una colección de objetos `IOperation` y se completará cuando se cree `MySimpleCalculator`, al mismo tiempo que las importaciones de `Program`.</span><span class="sxs-lookup"><span data-stu-id="4d080-221">`MySimpleCalculator`, in turn, imports a collection of `IOperation` objects, and that import will be filled when `MySimpleCalculator` is created, at the same time as the imports of `Program`.</span></span> <span data-ttu-id="4d080-222">Si la clase `Add` declarara una importación más extensa, también tendría que completarse, y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="4d080-222">If the `Add` class declared a further import, that too would have to be filled, and so on.</span></span> <span data-ttu-id="4d080-223">Toda importación que quede incompleta dará error en la composición.</span><span class="sxs-lookup"><span data-stu-id="4d080-223">Any import left unfilled results in a composition error.</span></span>  <span data-ttu-id="4d080-224">(Es posible, sin embargo, declarar las importaciones para que sean opcionales o asignarles valores predeterminados).</span><span class="sxs-lookup"><span data-stu-id="4d080-224">(It is possible, however, to declare imports to be optional or to assign them default values.)</span></span>  
  
<a name="calculator_logic"></a>   
## <a name="calculator-logic"></a><span data-ttu-id="4d080-225">Lógica de calculadora</span><span class="sxs-lookup"><span data-stu-id="4d080-225">Calculator Logic</span></span>  
 <span data-ttu-id="4d080-226">Con estos componentes bien establecidos, todo lo que queda es la propia lógica de la calculadora.</span><span class="sxs-lookup"><span data-stu-id="4d080-226">With these parts in place, all that remains is the calculator logic itself.</span></span> <span data-ttu-id="4d080-227">Agregue el código siguiente a la clase `MySimpleCalculator` para implementar el método `Calculate`:</span><span class="sxs-lookup"><span data-stu-id="4d080-227">Add the following code in the `MySimpleCalculator` class to implement the `Calculate` method:</span></span>  
  
```vb  
Public Function Calculate(ByVal input As String) As String Implements ICalculator.Calculate  
    Dim left, right As Integer  
    Dim operation As Char  
    Dim fn = FindFirstNonDigit(input) 'Finds the operator  
    If fn < 0 Then  
        Return "Could not parse command."  
    End If  
    operation = input(fn)  
    Try  
        left = Integer.Parse(input.Substring(0, fn))  
        right = Integer.Parse(input.Substring(fn + 1))  
    Catch ex As Exception  
        Return "Could not parse command."  
    End Try  
    For Each i As Lazy(Of IOperation, IOperationData) In operations  
        If i.Metadata.symbol = operation Then  
            Return i.Value.Operate(left, right).ToString()  
        End If  
    Next  
    Return "Operation not found!"  
End Function  
```  
  
```csharp  
public String Calculate(String input)  
{  
    int left;  
    int right;  
    Char operation;  
    int fn = FindFirstNonDigit(input); //finds the operator  
    if (fn < 0) return "Could not parse command.";  
  
    try  
    {  
        //separate out the operands  
        left = int.Parse(input.Substring(0, fn));  
        right = int.Parse(input.Substring(fn + 1));  
    }  
    catch   
    {  
        return "Could not parse command.";  
    }  
  
    operation = input[fn];  
  
    foreach (Lazy<IOperation, IOperationData> i in operations)  
    {  
        if (i.Metadata.Symbol.Equals(operation)) return i.Value.Operate(left, right).ToString();  
    }  
    return "Operation Not Found!";  
}  
```  
  
 <span data-ttu-id="4d080-228">Los pasos iniciales analizan la cadena de entrada en los operandos izquierdo y derecho, y un carácter de operador.</span><span class="sxs-lookup"><span data-stu-id="4d080-228">The initial steps parse the input string into left and right operands and an operator character.</span></span>  <span data-ttu-id="4d080-229">En el bucle de `foreach`, se examina cada miembro de la colección `operations`.</span><span class="sxs-lookup"><span data-stu-id="4d080-229">In the `foreach` loop, every member of the `operations` collection is examined.</span></span> <span data-ttu-id="4d080-230">Estos objetos son de tipo <xref:System.Lazy%602>; se puede obtener acceso a los valores de sus metadatos y al objeto exportado con las propiedades <xref:System.Lazy%602.Metadata%2A> y <xref:System.Lazy%601.Value%2A>, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="4d080-230">These objects are of type <xref:System.Lazy%602>, and their metadata values and exported object can be accessed with the <xref:System.Lazy%602.Metadata%2A> property and the <xref:System.Lazy%601.Value%2A> property respectively.</span></span> <span data-ttu-id="4d080-231">En este caso, si la propiedad `Symbol` del objeto `IOperationData` se detecta como una coincidencia, la calculadora llama al método `Operate` del objeto `IOperation` y devuelve el resultado.</span><span class="sxs-lookup"><span data-stu-id="4d080-231">In this case, if the `Symbol` property of the `IOperationData` object is discovered to be a match, the calculator calls the `Operate` method of the `IOperation` object and returns the result.</span></span>  
  
 <span data-ttu-id="4d080-232">Para completar la calculadora, también necesita un método auxiliar que devuelve la posición del primer carácter de una cadena que no sea un dígito.</span><span class="sxs-lookup"><span data-stu-id="4d080-232">To complete the calculator, you also need a helper method that returns the position of the first non-digit character in a string.</span></span>  <span data-ttu-id="4d080-233">Agregue el método auxiliar siguiente a la clase `MySimpleCalculator`:</span><span class="sxs-lookup"><span data-stu-id="4d080-233">Add the following helper method to the `MySimpleCalculator` class:</span></span>  
  
```vb  
Private Function FindFirstNonDigit(ByVal s As String) As Integer  
    For i = 0 To s.Length  
        If (Not (Char.IsDigit(s(i)))) Then Return i  
    Next  
    Return -1  
End Function  
```  
  
```csharp  
private int FindFirstNonDigit(String s)  
{  
    for (int i = 0; i < s.Length; i++)  
    {  
        if (!(Char.IsDigit(s[i]))) return i;  
    }  
    return -1;  
}  
```  
  
 <span data-ttu-id="4d080-234">A partir de este momento, podrá compilar e implementar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="4d080-234">You should now be able to compile and run the project.</span></span> <span data-ttu-id="4d080-235">En Visual Basic, asegúrese de que ha agregado la palabra clave `Public` a `Module1`.</span><span class="sxs-lookup"><span data-stu-id="4d080-235">In Visual Basic, make sure that you added the `Public` keyword to `Module1`.</span></span> <span data-ttu-id="4d080-236">En la ventana de consola, escriba una operación de suma, como "5+3" y la calculadora devolverá los resultados.</span><span class="sxs-lookup"><span data-stu-id="4d080-236">In the console window, type an addition operation, such as "5+3", and the calculator will return the results.</span></span>  <span data-ttu-id="4d080-237">Cualquier otro operador dará lugar al mensaje "Operación no encontrada"</span><span class="sxs-lookup"><span data-stu-id="4d080-237">Any other operator will result in the "Operation Not Found!"</span></span> <span data-ttu-id="4d080-238">.</span><span class="sxs-lookup"><span data-stu-id="4d080-238">message.</span></span>  
  
<a name="extending_simplecalculator_using_a_new_class"></a>   
## <a name="extending-simplecalculator-using-a-new-class"></a><span data-ttu-id="4d080-239">Extender SimpleCalculator utilizando una clase nueva</span><span class="sxs-lookup"><span data-stu-id="4d080-239">Extending SimpleCalculator Using A New Class</span></span>  
 <span data-ttu-id="4d080-240">Ahora que la calculadora funciona, agregar una nueva operación es fácil.</span><span class="sxs-lookup"><span data-stu-id="4d080-240">Now that the calculator works, adding a new operation is easy.</span></span> <span data-ttu-id="4d080-241">Agregue la siguiente clase al módulo o al espacio de nombres `SimpleCalculator`:</span><span class="sxs-lookup"><span data-stu-id="4d080-241">Add the following class to the module or `SimpleCalculator` namespace:</span></span>  
  
```vb  
<Export(GetType(IOperation))>  
<ExportMetadata("Symbol", "-"c)>  
Public Class Subtract  
    Implements IOperation  
  
    Public Function Operate(ByVal left As Integer, ByVal right As Integer) As Integer Implements IOperation.Operate  
        Return left - right  
    End Function  
End Class  
```  
  
```csharp  
[Export(typeof(IOperation))]  
[ExportMetadata("Symbol", '-')]  
class Subtract : IOperation  
{  
    public int Operate(int left, int right)  
    {  
        return left - right;  
    }  
}  
```  
  
 <span data-ttu-id="4d080-242">Compile y ejecute el proyecto.</span><span class="sxs-lookup"><span data-stu-id="4d080-242">Compile and run the project.</span></span> <span data-ttu-id="4d080-243">Escriba una operación de resta, como "5-3".</span><span class="sxs-lookup"><span data-stu-id="4d080-243">Type a subtraction operation, such as "5-3".</span></span> <span data-ttu-id="4d080-244">La calculadora admite ahora la resta además de la suma.</span><span class="sxs-lookup"><span data-stu-id="4d080-244">The calculator now supports subtraction as well as addition.</span></span>  
  
<a name="extending_simplecalculator_using_a_new_assembly"></a>   
## <a name="extending-simplecalculator-using-a-new-assembly"></a><span data-ttu-id="4d080-245">Extender SimpleCalculator con un nuevo ensamblado</span><span class="sxs-lookup"><span data-stu-id="4d080-245">Extending SimpleCalculator Using A New Assembly</span></span>  
 <span data-ttu-id="4d080-246">Agregar clases al código fuente es bastante sencillo, pero MEF permite buscar elementos fuera del propio origen de una aplicación.</span><span class="sxs-lookup"><span data-stu-id="4d080-246">Adding classes to the source code is simple enough, but MEF provides the ability to look outside an application’s own source for parts.</span></span> <span data-ttu-id="4d080-247">Para demostrar esto, necesitará modificar SimpleCalculator para que busque los elementos en un directorio y en su propio ensamblado agregando <xref:System.ComponentModel.Composition.Hosting.DirectoryCatalog>.</span><span class="sxs-lookup"><span data-stu-id="4d080-247">To demonstrate this, you will need to modify SimpleCalculator to search a directory, as well as its own assembly, for parts, by adding a <xref:System.ComponentModel.Composition.Hosting.DirectoryCatalog>.</span></span>  
  
 <span data-ttu-id="4d080-248">Agregue un directorio denominado `Extensions` al proyecto SimpleCalculator.</span><span class="sxs-lookup"><span data-stu-id="4d080-248">Add a new directory named `Extensions` to the SimpleCalculator project.</span></span>  <span data-ttu-id="4d080-249">Asegúrese de agregarlo en el nivel del proyecto y no en el nivel de la solución.</span><span class="sxs-lookup"><span data-stu-id="4d080-249">Make sure to add it at the project level, and not at the solution level.</span></span> <span data-ttu-id="4d080-250">Después agregue a la solución un proyecto de biblioteca de clases denominado `ExtendedOperations`.</span><span class="sxs-lookup"><span data-stu-id="4d080-250">Then add a new Class Library project to the solution, named `ExtendedOperations`.</span></span> <span data-ttu-id="4d080-251">El nuevo proyecto se compilará en un ensamblado independiente.</span><span class="sxs-lookup"><span data-stu-id="4d080-251">The new project will compile into a separate assembly.</span></span>  
  
 <span data-ttu-id="4d080-252">Abra el diseñador de propiedades de proyectos para el proyecto ExtendedOperations y haga clic en la pestaña **Compilar** o **Compilación**. Cambie **Ruta de acceso de los resultados de la compilación** o **Ruta de acceso de salida** para que apunte al directorio Extensions del directorio del proyecto SimpleCalculator (..\SimpleCalculator\Extensions\\).</span><span class="sxs-lookup"><span data-stu-id="4d080-252">Open the Project Properties Designer for the ExtendedOperations project and click the **Compile** or **Build** tab. Change the **Build output path** or **Output path** to point to the Extensions directory in the SimpleCalculator project directory (..\SimpleCalculator\Extensions\\).</span></span>  
  
 <span data-ttu-id="4d080-253">En Module1.vb o Program.cs, agregue la línea siguiente al constructor `Program`:</span><span class="sxs-lookup"><span data-stu-id="4d080-253">In Module1.vb or Program.cs, add the following line to the `Program` constructor:</span></span>  
  
```vb  
catalog.Catalogs.Add(New DirectoryCatalog("C:\SimpleCalculator\SimpleCalculator\Extensions"))  
```  
  
```csharp  
catalog.Catalogs.Add(new DirectoryCatalog("C:\\SimpleCalculator\\SimpleCalculator\\Extensions"));  
```  
  
 <span data-ttu-id="4d080-254">Reemplace la ruta de acceso del ejemplo por la ruta de acceso del directorio Extensions.</span><span class="sxs-lookup"><span data-stu-id="4d080-254">Replace the example path with the path to your Extensions directory.</span></span>  <span data-ttu-id="4d080-255">(Esta ruta de acceso absoluta es para fines de depuración solamente.</span><span class="sxs-lookup"><span data-stu-id="4d080-255">(This absolute path is for debugging purposes only.</span></span>  <span data-ttu-id="4d080-256">En una aplicación de producción, usaría una ruta de acceso relativa). <xref:System.ComponentModel.Composition.Hosting.DirectoryCatalog> agregará los elementos encontrados en cualquier ensamblado del directorio Extensions al contenedor de composición.</span><span class="sxs-lookup"><span data-stu-id="4d080-256">In a production application, you would use a relative path.) The <xref:System.ComponentModel.Composition.Hosting.DirectoryCatalog> will now add any parts found in any assemblies in the Extensions directory to the composition container.</span></span>  
  
 <span data-ttu-id="4d080-257">En el proyecto ExtendedOperations, agregue referencias a SimpleCalculator y System.ComponentModel.Composition.</span><span class="sxs-lookup"><span data-stu-id="4d080-257">In the ExtendedOperations project, add references to SimpleCalculator and System.ComponentModel.Composition.</span></span> <span data-ttu-id="4d080-258">En el archivo de clase ExtendedOperations, agregue una instrucción `Imports` o `using` para System.ComponentModel.Composition.</span><span class="sxs-lookup"><span data-stu-id="4d080-258">In the ExtendedOperations class file, add an `Imports` or a `using` statement for System.ComponentModel.Composition.</span></span> <span data-ttu-id="4d080-259">En Visual Basic, agregue también una instrucción `Imports` para SimpleCalculator.</span><span class="sxs-lookup"><span data-stu-id="4d080-259">In Visual Basic, also add an `Imports` statement for SimpleCalculator.</span></span> <span data-ttu-id="4d080-260">Después, agregue la clase siguiente al archivo de clase ExtendedOperations:</span><span class="sxs-lookup"><span data-stu-id="4d080-260">Then add the following class to the ExtendedOperations class file:</span></span>  
  
```vb  
<Export(GetType(SimpleCalculator.IOperation))>  
<ExportMetadata("Symbol", "%"c)>  
Public Class Modulo  
    Implements IOperation  
  
    Public Function Operate(ByVal left As Integer, ByVal right As Integer) As Integer Implements IOperation.Operate  
        Return left Mod right  
    End Function  
End Class  
```  
  
```csharp  
[Export(typeof(SimpleCalculator.IOperation))]  
[ExportMetadata("Symbol", '%')]  
public class Mod : SimpleCalculator.IOperation  
{  
    public int Operate(int left, int right)  
    {  
        return left % right;  
    }  
}  
```  
  
 <span data-ttu-id="4d080-261">Tenga en cuenta que para que el contrato coincida, el atributo <xref:System.ComponentModel.Composition.ExportAttribute> debe tener el mismo tipo que <xref:System.ComponentModel.Composition.ImportAttribute>.</span><span class="sxs-lookup"><span data-stu-id="4d080-261">Note that in order for the contract to match, the <xref:System.ComponentModel.Composition.ExportAttribute> attribute must have the same type as the <xref:System.ComponentModel.Composition.ImportAttribute>.</span></span>  
  
 <span data-ttu-id="4d080-262">Compile y ejecute el proyecto.</span><span class="sxs-lookup"><span data-stu-id="4d080-262">Compile and run the project.</span></span> <span data-ttu-id="4d080-263">Pruebe el nuevo operador Mod (%).</span><span class="sxs-lookup"><span data-stu-id="4d080-263">Test the new Mod (%) operator.</span></span>  
  
<a name="conclusion"></a>   
## <a name="conclusion"></a><span data-ttu-id="4d080-264">Conclusión</span><span class="sxs-lookup"><span data-stu-id="4d080-264">Conclusion</span></span>  
 <span data-ttu-id="4d080-265">En este tema se han tratado los conceptos básicos de MEF.</span><span class="sxs-lookup"><span data-stu-id="4d080-265">This topic covered the basic concepts of MEF.</span></span>  
  
-   <span data-ttu-id="4d080-266">Elementos, catálogos y el contenedor de composición</span><span class="sxs-lookup"><span data-stu-id="4d080-266">Parts, catalogs, and the composition container</span></span>  
  
     <span data-ttu-id="4d080-267">Los elementos y el contenedor de composición son los pilares fundamentales de una aplicación MEF.</span><span class="sxs-lookup"><span data-stu-id="4d080-267">Parts and the composition container are the basic building blocks of a MEF application.</span></span> <span data-ttu-id="4d080-268">Un elemento es cualquier objeto que importa o exporta un valor, hasta sí mismo incluido.</span><span class="sxs-lookup"><span data-stu-id="4d080-268">A part is any object that imports or exports a value, up to and including itself.</span></span> <span data-ttu-id="4d080-269">Un catálogo proporciona una colección de elementos de un origen determinado.</span><span class="sxs-lookup"><span data-stu-id="4d080-269">A catalog provides a collection of parts from a particular source.</span></span>  <span data-ttu-id="4d080-270">El contenedor de composición utiliza los elementos proporcionados por un catálogo para realizar la composición, el enlace de las importaciones a las exportaciones.</span><span class="sxs-lookup"><span data-stu-id="4d080-270">The composition container uses the parts provided by a catalog to perform composition, the binding of imports to exports.</span></span>  
  
-   <span data-ttu-id="4d080-271">Importaciones y exportaciones</span><span class="sxs-lookup"><span data-stu-id="4d080-271">Imports and exports</span></span>  
  
     <span data-ttu-id="4d080-272">Las importaciones y las exportaciones son la manera en la que los componentes se comunican.</span><span class="sxs-lookup"><span data-stu-id="4d080-272">Imports and exports are the way by which components communicate.</span></span> <span data-ttu-id="4d080-273">Con una importación, el componente especifica la necesidad de un valor u objeto determinado, y con una exportación se especifica la disponibilidad de un valor.</span><span class="sxs-lookup"><span data-stu-id="4d080-273">With an import, the component specifies a need for a particular value or object, and with an export it specifies the availability of a value.</span></span> <span data-ttu-id="4d080-274">Cada importación coincide con una lista de exportaciones por medio de su contrato.</span><span class="sxs-lookup"><span data-stu-id="4d080-274">Each import is matched with a list of exports by way of its contract.</span></span>  
  
<a name="where_do_i_go_now"></a>   
## <a name="where-do-i-go-now"></a><span data-ttu-id="4d080-275">¿Por dónde seguir?</span><span class="sxs-lookup"><span data-stu-id="4d080-275">Where Do I Go Now?</span></span>  
 <span data-ttu-id="4d080-276">Para descargar el código completo de este ejemplo, consulte [Ejemplo SimpleCalculator](https://code.msdn.microsoft.com/windowsdesktop/Simple-Calculator-MEF-1152654e).</span><span class="sxs-lookup"><span data-stu-id="4d080-276">To download the complete code for this example, see the [SimpleCalculator sample](https://code.msdn.microsoft.com/windowsdesktop/Simple-Calculator-MEF-1152654e).</span></span>  
  
 <span data-ttu-id="4d080-277">Para obtener más información y ejemplos de código, consulte [Managed Extensibility Framework](https://go.microsoft.com/fwlink/?LinkId=144282).</span><span class="sxs-lookup"><span data-stu-id="4d080-277">For more information and code examples, see [Managed Extensibility Framework](https://go.microsoft.com/fwlink/?LinkId=144282).</span></span> <span data-ttu-id="4d080-278">Para obtener una lista de los tipos de MEF, vea el espacio de nombres <xref:System.ComponentModel.Composition?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4d080-278">For a list of the MEF types, see the <xref:System.ComponentModel.Composition?displayProperty=nameWithType> namespace.</span></span>
