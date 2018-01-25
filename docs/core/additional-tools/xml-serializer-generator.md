---
title: Usar el generador de serializador XML de Microsoft en .NET Core
description: "Información general sobre el generador de serializador XML de Microsoft."
author: mlacouture
manager: wpickett
ms.author: johalex
ms.date: 01/19/2017
ms.topic: tutorial
ms.prod: .net-core
ms.custom: mvc
ms.openlocfilehash: 4b838cafe1f4835c1c5aa6086c0997a4a9e39a9e
ms.sourcegitcommit: 8bde7a3432f30fc771079744955c75c58c4eb393
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/20/2018
---
# <a name="using-microsoft-xml-serializer-generator-on-net-core"></a><span data-ttu-id="597b1-103">Usar el generador de serializador XML de Microsoft en .NET Core</span><span class="sxs-lookup"><span data-stu-id="597b1-103">Using Microsoft XML Serializer Generator on .NET Core</span></span>

<span data-ttu-id="597b1-104">Este tutorial muestra cómo usar el generador de serializador XML de Microsoft en una aplicación .NET Core de C#.</span><span class="sxs-lookup"><span data-stu-id="597b1-104">This tutorial teaches you how to use the Microsoft XML Serializer Generator in a C# .NET Core application.</span></span> <span data-ttu-id="597b1-105">Este tutorial ayuda a:</span><span class="sxs-lookup"><span data-stu-id="597b1-105">During the course of this tutorial, you learn:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="597b1-106">Cómo crear una aplicación .NET Core</span><span class="sxs-lookup"><span data-stu-id="597b1-106">How to create a .NET Core app</span></span>
> * <span data-ttu-id="597b1-107">Cómo agregar una referencia al paquete Microsoft.XmlSerializer.Generator</span><span class="sxs-lookup"><span data-stu-id="597b1-107">How to add a reference to the Microsoft.XmlSerializer.Generator package</span></span>
> * <span data-ttu-id="597b1-108">Cómo editar MyApp.csproj para agregar dependencias</span><span class="sxs-lookup"><span data-stu-id="597b1-108">How to edit your MyApp.csproj to add dependencies</span></span>
> * <span data-ttu-id="597b1-109">Cómo agregar una clase y un XmlSerializer</span><span class="sxs-lookup"><span data-stu-id="597b1-109">How to add a class and an XmlSerializer</span></span>
> * <span data-ttu-id="597b1-110">Cómo compilar y ejecutar la aplicación</span><span class="sxs-lookup"><span data-stu-id="597b1-110">How to build and run the application</span></span> 

<span data-ttu-id="597b1-111">Tal y como sucede con el [generador de serializador de XML (sgen.exe)](../../standard/serialization/xml-serializer-generator-tool-sgen-exe.md) para .NET Framework, el [paquete Microsoft.XmlSerializer.Generator de NuGet ](https://www.nuget.org/packages/Microsoft.XmlSerializer.Generator) es el equivalente para proyectos de .NET Core y .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="597b1-111">Like the [Xml Serializer Generator (sgen.exe)](../../standard/serialization/xml-serializer-generator-tool-sgen-exe.md) for the .NET Framework, the [Microsoft.XmlSerializer.Generator NuGet package](https://www.nuget.org/packages/Microsoft.XmlSerializer.Generator) is the equivalent for .NET Core and .NET Standard projects.</span></span> <span data-ttu-id="597b1-112">Crea un ensamblado de serialización de XML para los tipos incluidos en un ensamblado para mejorar el rendimiento de inicio de la serialización XML al serializar o deserializar objetos de esos tipos con <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="597b1-112">It creates an XML serialization assembly for types contained in an assembly to improve the startup performance of XML serialization when serializing or de-serializing objects of those types using <xref:System.Xml.Serialization.XmlSerializer>.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="597b1-113">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="597b1-113">Prerequisites</span></span>

<span data-ttu-id="597b1-114">Para realizar este tutorial:</span><span class="sxs-lookup"><span data-stu-id="597b1-114">To complete this tutorial:</span></span>

* <span data-ttu-id="597b1-115">Instalar [.NET Core SDK 2.1.3 o posterior](https://www.microsoft.com/net/download)</span><span class="sxs-lookup"><span data-stu-id="597b1-115">Install [.NET Core SDK 2.1.3 or later](https://www.microsoft.com/net/download)</span></span>
* <span data-ttu-id="597b1-116">Instale el editor de código que prefiera si aún no lo ha hecho.</span><span class="sxs-lookup"><span data-stu-id="597b1-116">Install your favorite code editor, if you haven't already.</span></span>

> [!TIP]
> <span data-ttu-id="597b1-117">¿Es necesario instalar un editor de código?</span><span class="sxs-lookup"><span data-stu-id="597b1-117">Need to install a code editor?</span></span> <span data-ttu-id="597b1-118">Pruebe [Visual Studio](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs).</span><span class="sxs-lookup"><span data-stu-id="597b1-118">Try [Visual Studio](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)!</span></span>
  
## <a name="use-microsoft-xml-serializer-generator-in-a-net-core-console-application"></a><span data-ttu-id="597b1-119">Usar el generador de serializador de XML de Microsoft en una aplicación de consola .NET Core</span><span class="sxs-lookup"><span data-stu-id="597b1-119">Use Microsoft XML Serializer Generator in a .NET Core console application</span></span> 

<span data-ttu-id="597b1-120">Las instrucciones siguientes muestran cómo usar el generador de serializador XML en una aplicación de consola .NET Core.</span><span class="sxs-lookup"><span data-stu-id="597b1-120">The following instructions show you how to use XML Serializer Generator in a .NET Core console application.</span></span>

### <a name="create-a-net-core-console-application"></a><span data-ttu-id="597b1-121">Creación de una aplicación de consola .NET Core</span><span class="sxs-lookup"><span data-stu-id="597b1-121">Create a .NET Core console application</span></span>

<span data-ttu-id="597b1-122">Abra un símbolo del sistema y cree una carpeta denominada *MyApp*.</span><span class="sxs-lookup"><span data-stu-id="597b1-122">Open a command prompt and create a folder named *MyApp*.</span></span> <span data-ttu-id="597b1-123">Vaya a la carpeta que creó y escriba estos comandos:</span><span class="sxs-lookup"><span data-stu-id="597b1-123">Navigate to the folder you created and type the following command:</span></span>

```console
dotnet new console
```

### <a name="add-a-reference-to-the-microsoftxmlserializergenerator-package-in-the-myapp-project"></a><span data-ttu-id="597b1-124">Agregue una referencia al paquete Microsoft.XmlSerializer.Generator en el proyecto de MyApp</span><span class="sxs-lookup"><span data-stu-id="597b1-124">Add a reference to the Microsoft.XmlSerializer.Generator package in the MyApp project</span></span>

<span data-ttu-id="597b1-125">Use el comando [`dotnet add package`](../tools//dotnet-add-package.md) para agregar la referencia en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="597b1-125">Use the [`dotnet add package`](../tools//dotnet-add-package.md) command to add the reference in your project.</span></span> 

<span data-ttu-id="597b1-126">Tipo:</span><span class="sxs-lookup"><span data-stu-id="597b1-126">Type:</span></span>
 
 ```console
 dotnet add package Microsoft.XmlSerializer.Generator -v 1.0.0
 ```
 
### <a name="verify-changes-to-myappcsproj-after-adding-the-package"></a><span data-ttu-id="597b1-127">Comprobar los cambios en MyApp.csproj después de agregar el paquete</span><span class="sxs-lookup"><span data-stu-id="597b1-127">Verify changes to MyApp.csproj after adding the package</span></span>

<span data-ttu-id="597b1-128">Abra el editor de código para empezar.</span><span class="sxs-lookup"><span data-stu-id="597b1-128">Open your code editor and let's get started!</span></span> <span data-ttu-id="597b1-129">Todavía estamos trabajando desde el directorio *MyApp* en el que hemos compilado la aplicación.</span><span class="sxs-lookup"><span data-stu-id="597b1-129">We're still working from the *MyApp* directory we built the app in.</span></span>

<span data-ttu-id="597b1-130">Abra *MyApp.csproj* en el editor de texto.</span><span class="sxs-lookup"><span data-stu-id="597b1-130">Open *MyApp.csproj* in your text editor.</span></span>

<span data-ttu-id="597b1-131">Después de ejecutar el comando [`dotnet add package`](../tools//dotnet-add-package.md), se agregan estas líneas al archivo de proyecto *MyApp.csproj*:</span><span class="sxs-lookup"><span data-stu-id="597b1-131">After running the [`dotnet add package`](../tools//dotnet-add-package.md) command, the following lines are added to your *MyApp.csproj* project file:</span></span>

 ```xml
 <ItemGroup>
    <PackageReference Include="Microsoft.XmlSerializer.Generator" Version="1.0.0" />
 </ItemGroup>
 ```
 
### <a name="add-another-itemgroup-section-for-net-core-cli-tool-support"></a><span data-ttu-id="597b1-132">Agregar otra sección ItemGroup para admitir la herramienta CLI de .NET Core</span><span class="sxs-lookup"><span data-stu-id="597b1-132">Add another ItemGroup section for .NET Core CLI Tool support</span></span>
 
 <span data-ttu-id="597b1-133">Agregue estas líneas después de la sección `ItemGroup` que hemos inspeccionado:</span><span class="sxs-lookup"><span data-stu-id="597b1-133">Add the following lines after the `ItemGroup` section that we inspected:</span></span>
 
 ```xml
 <ItemGroup>
    <DotNetCliToolReference Include="Microsoft.XmlSerializer.Generator" Version="1.0.0" />
 </ItemGroup>
 ```
 
### <a name="add-a-class-in-the-application"></a><span data-ttu-id="597b1-134">Agregar una clase en la aplicación</span><span class="sxs-lookup"><span data-stu-id="597b1-134">Add a class in the application</span></span>

<span data-ttu-id="597b1-135">Abra *Program.cs* en el editor de texto.</span><span class="sxs-lookup"><span data-stu-id="597b1-135">Open *Program.cs* in your text editor.</span></span> <span data-ttu-id="597b1-136">Agregue la clase con el nombre *MyClass* en *Program.cs*.</span><span class="sxs-lookup"><span data-stu-id="597b1-136">Add the class named *MyClass* in *Program.cs*.</span></span>

```csharp
public class MyClass
{
   public int Value;
}
```

### <a name="create-an-xmlserializer-for-myclass"></a><span data-ttu-id="597b1-137">Crear un `XmlSerializer` para MyClass</span><span class="sxs-lookup"><span data-stu-id="597b1-137">Create an `XmlSerializer` for MyClass</span></span>

<span data-ttu-id="597b1-138">Agregue esta línea dentro de *Main* para crear un `XmlSerializer` para MyClass:</span><span class="sxs-lookup"><span data-stu-id="597b1-138">Add the following line inside *Main* to create an `XmlSerializer` for MyClass:</span></span>

```csharp
var serializer = new System.Xml.Serialization.XmlSerializer(typeof(MyClass));
```

### <a name="build-and-run-the-application"></a><span data-ttu-id="597b1-139">Compilar y ejecutar la aplicación</span><span class="sxs-lookup"><span data-stu-id="597b1-139">Build and run the application</span></span>

<span data-ttu-id="597b1-140">Seguimos en la carpeta *MyApp*, desde donde vamos a ejecutar la aplicación a través de [`dotnet run`](../tools/dotnet-run.md). Se carga automáticamente y usa los serializadores generados previamente en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="597b1-140">Still within the *MyApp* folder, run the application via [`dotnet run`](../tools/dotnet-run.md) and it automatically loads and uses the pre-generated serializers at runtime.</span></span>

<span data-ttu-id="597b1-141">Escriba el siguiente comando en la ventana de consola:</span><span class="sxs-lookup"><span data-stu-id="597b1-141">Type the following command in your console window:</span></span>

 ```console
 $ dotnet run
 ```
> [!NOTE]
> <span data-ttu-id="597b1-142">[`dotnet run`](../tools/dotnet-run.md) llama a [`dotnet build`](../tools/dotnet-build.md) para asegurarse de que los destinos de la compilación se han creado y, después, llama a `dotnet <assembly.dll>` para ejecutar la aplicación de destino.</span><span class="sxs-lookup"><span data-stu-id="597b1-142">[`dotnet run`](../tools/dotnet-run.md) calls [`dotnet build`](../tools/dotnet-build.md) to ensure that the build targets have been built, and then calls `dotnet <assembly.dll>` to run the target application.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="597b1-143">Los comandos y los pasos que se muestran en este tutorial para ejecutar la aplicación se usan solo durante el desarrollo.</span><span class="sxs-lookup"><span data-stu-id="597b1-143">The commands and steps shown in this tutorial to run your application are used during development time only.</span></span> <span data-ttu-id="597b1-144">Una vez que esté listo para implementar la aplicación, eche un vistazo a las diferentes [estrategias de implementación](../deploying/index.md) para aplicaciones .NET Core y al comando [`dotnet publish`](../tools/dotnet-publish.md).</span><span class="sxs-lookup"><span data-stu-id="597b1-144">Once you're ready to deploy your app, take a look at the different [deployment strategies](../deploying/index.md) for .NET Core apps and the [`dotnet publish`](../tools/dotnet-publish.md) command.</span></span>

<span data-ttu-id="597b1-145">Si todo se realiza correctamente, se genera un ensamblado con el nombre *.dll MyApp.XmlSerializers.dll* en la carpeta de salida.</span><span class="sxs-lookup"><span data-stu-id="597b1-145">If everything succeeds, an assembly named *MyApp.XmlSerializers.dll* is generated in the output folder.</span></span> 



<span data-ttu-id="597b1-146">¡Enhorabuena!</span><span class="sxs-lookup"><span data-stu-id="597b1-146">Congratulations!</span></span> <span data-ttu-id="597b1-147">Acaba de:</span><span class="sxs-lookup"><span data-stu-id="597b1-147">You have just:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="597b1-148">Crear una aplicación .NET Core.</span><span class="sxs-lookup"><span data-stu-id="597b1-148">Created a .NET Core app.</span></span>
> * <span data-ttu-id="597b1-149">Agregar una referencia al paquete Microsoft.XmlSerializer.Generator.</span><span class="sxs-lookup"><span data-stu-id="597b1-149">Added a reference to the Microsoft.XmlSerializer.Generator package.</span></span>
> * <span data-ttu-id="597b1-150">Editar MyApp.csproj para agregar dependencias.</span><span class="sxs-lookup"><span data-stu-id="597b1-150">Edited your MyApp.csproj to add dependencies.</span></span>
> * <span data-ttu-id="597b1-151">Agregue una clase y un XmlSerializer.</span><span class="sxs-lookup"><span data-stu-id="597b1-151">Added a class and an XmlSerializer.</span></span>
> * <span data-ttu-id="597b1-152">Compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="597b1-152">Built and ran the application.</span></span> 

## <a name="related-resources"></a><span data-ttu-id="597b1-153">Recursos relacionados</span><span class="sxs-lookup"><span data-stu-id="597b1-153">Related Resources</span></span>

* [<span data-ttu-id="597b1-154">Introducción a la serialización XML</span><span class="sxs-lookup"><span data-stu-id="597b1-154">Introducing XML Serialization</span></span>](../../standard/serialization/introducing-xml-serialization.md)
* <span data-ttu-id="597b1-155">[How to: Serialize Using XmlSerializer (C#)](../../csharp/programming-guide/concepts/linq/how-to-serialize-using-xmlserializer) (Cómo: Serializar con XmlSerializer (C#))</span><span class="sxs-lookup"><span data-stu-id="597b1-155">[How to: Serialize Using XmlSerializer (C#)](../../csharp/programming-guide/concepts/linq/how-to-serialize-using-xmlserializer)</span></span>
* [<span data-ttu-id="597b1-156">Cómo: serializar con XmlSerializer (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="597b1-156">How to: Serialize Using XmlSerializer (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/linq/how-to-serialize-using-xmlserializer)