---
title: Generador de serializador XML de Microsoft
description: Información general sobre el generador de serializador XML de Microsoft. Use el generador de serializador XML para generar un ensamblado de serialización XML para los tipos contenidos en el proyecto.
author: mlacouture
ms.date: 01/19/2017
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 8005a8a3e5202b0255ec482dfb7e3c284bc2e19b
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90538909"
---
# <a name="using-microsoft-xml-serializer-generator-on-net-core"></a><span data-ttu-id="fc566-104">Usar el generador de serializador XML de Microsoft en .NET Core</span><span class="sxs-lookup"><span data-stu-id="fc566-104">Using Microsoft XML Serializer Generator on .NET Core</span></span>

<span data-ttu-id="fc566-105">Este tutorial muestra cómo usar el generador de serializador XML de Microsoft en una aplicación .NET Core de C#.</span><span class="sxs-lookup"><span data-stu-id="fc566-105">This tutorial teaches you how to use the Microsoft XML Serializer Generator in a C# .NET Core application.</span></span> <span data-ttu-id="fc566-106">Este tutorial ayuda a:</span><span class="sxs-lookup"><span data-stu-id="fc566-106">During the course of this tutorial, you learn:</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="fc566-107">Cómo crear una aplicación .NET Core</span><span class="sxs-lookup"><span data-stu-id="fc566-107">How to create a .NET Core app</span></span>
> - <span data-ttu-id="fc566-108">Cómo agregar una referencia al paquete Microsoft.XmlSerializer.Generator</span><span class="sxs-lookup"><span data-stu-id="fc566-108">How to add a reference to the Microsoft.XmlSerializer.Generator package</span></span>
> - <span data-ttu-id="fc566-109">Cómo editar MyApp.csproj para agregar dependencias</span><span class="sxs-lookup"><span data-stu-id="fc566-109">How to edit your MyApp.csproj to add dependencies</span></span>
> - <span data-ttu-id="fc566-110">Cómo agregar una clase y un XmlSerializer</span><span class="sxs-lookup"><span data-stu-id="fc566-110">How to add a class and an XmlSerializer</span></span>
> - <span data-ttu-id="fc566-111">Cómo compilar y ejecutar la aplicación</span><span class="sxs-lookup"><span data-stu-id="fc566-111">How to build and run the application</span></span>

<span data-ttu-id="fc566-112">Tal y como sucede con el [generador de serializador de XML (sgen.exe)](../../standard/serialization/xml-serializer-generator-tool-sgen-exe.md) para .NET Framework, el [paquete Microsoft.XmlSerializer.Generator de NuGet ](https://www.nuget.org/packages/Microsoft.XmlSerializer.Generator) es el equivalente para proyectos de .NET Core y .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="fc566-112">Like the [Xml Serializer Generator (sgen.exe)](../../standard/serialization/xml-serializer-generator-tool-sgen-exe.md) for the .NET Framework, the [Microsoft.XmlSerializer.Generator NuGet package](https://www.nuget.org/packages/Microsoft.XmlSerializer.Generator) is the equivalent for .NET Core and .NET Standard projects.</span></span> <span data-ttu-id="fc566-113">Crea un ensamblado de serialización de XML para los tipos contenidos en un ensamblado para mejorar el rendimiento de inicio de la serialización XML al serializar o deserializar objetos de esos tipos con <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="fc566-113">It creates an XML serialization assembly for types contained in an assembly to improve the startup performance of XML serialization when serializing or de-serializing objects of those types using <xref:System.Xml.Serialization.XmlSerializer>.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="fc566-114">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="fc566-114">Prerequisites</span></span>

<span data-ttu-id="fc566-115">Para realizar este tutorial:</span><span class="sxs-lookup"><span data-stu-id="fc566-115">To complete this tutorial:</span></span>

- <span data-ttu-id="fc566-116">[SDK de .NET Core 2.1](https://dotnet.microsoft.com/download) o versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="fc566-116">[.NET Core 2.1 SDK](https://dotnet.microsoft.com/download) or later.</span></span>
- <span data-ttu-id="fc566-117">Su editor de código favorito.</span><span class="sxs-lookup"><span data-stu-id="fc566-117">Your favorite code editor.</span></span>

> [!TIP]
> <span data-ttu-id="fc566-118">¿Es necesario instalar un editor de código?</span><span class="sxs-lookup"><span data-stu-id="fc566-118">Need to install a code editor?</span></span> <span data-ttu-id="fc566-119">Pruebe [Visual Studio](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs).</span><span class="sxs-lookup"><span data-stu-id="fc566-119">Try [Visual Studio](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs)!</span></span>

## <a name="use-microsoft-xml-serializer-generator-in-a-net-core-console-application"></a><span data-ttu-id="fc566-120">Usar el generador de serializador de XML de Microsoft en una aplicación de consola .NET Core</span><span class="sxs-lookup"><span data-stu-id="fc566-120">Use Microsoft XML Serializer Generator in a .NET Core console application</span></span>

<span data-ttu-id="fc566-121">Las instrucciones siguientes muestran cómo usar el generador de serializador XML en una aplicación de consola .NET Core.</span><span class="sxs-lookup"><span data-stu-id="fc566-121">The following instructions show you how to use XML Serializer Generator in a .NET Core console application.</span></span>

### <a name="create-a-net-core-console-application"></a><span data-ttu-id="fc566-122">Creación de una aplicación de consola .NET Core</span><span class="sxs-lookup"><span data-stu-id="fc566-122">Create a .NET Core console application</span></span>

<span data-ttu-id="fc566-123">Abra un símbolo del sistema y cree una carpeta denominada *MyApp*.</span><span class="sxs-lookup"><span data-stu-id="fc566-123">Open a command prompt and create a folder named *MyApp*.</span></span> <span data-ttu-id="fc566-124">Vaya a la carpeta que creó y escriba estos comandos:</span><span class="sxs-lookup"><span data-stu-id="fc566-124">Navigate to the folder you created and type the following command:</span></span>

```dotnetcli
dotnet new console
```

### <a name="add-a-reference-to-the-microsoftxmlserializergenerator-package-in-the-myapp-project"></a><span data-ttu-id="fc566-125">Agregue una referencia al paquete Microsoft.XmlSerializer.Generator en el proyecto de MyApp</span><span class="sxs-lookup"><span data-stu-id="fc566-125">Add a reference to the Microsoft.XmlSerializer.Generator package in the MyApp project</span></span>

<span data-ttu-id="fc566-126">Use el comando [`dotnet add package`](../tools/dotnet-add-package.md) para agregar la referencia en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="fc566-126">Use the [`dotnet add package`](../tools/dotnet-add-package.md) command to add the reference in your project.</span></span>

<span data-ttu-id="fc566-127">Tipo:</span><span class="sxs-lookup"><span data-stu-id="fc566-127">Type:</span></span>

```dotnetcli
dotnet add package Microsoft.XmlSerializer.Generator -v 1.0.0
```

### <a name="verify-changes-to-myappcsproj-after-adding-the-package"></a><span data-ttu-id="fc566-128">Comprobar los cambios en MyApp.csproj después de agregar el paquete</span><span class="sxs-lookup"><span data-stu-id="fc566-128">Verify changes to MyApp.csproj after adding the package</span></span>

<span data-ttu-id="fc566-129">Abra el editor de código para empezar.</span><span class="sxs-lookup"><span data-stu-id="fc566-129">Open your code editor and let's get started!</span></span> <span data-ttu-id="fc566-130">Todavía estamos trabajando desde el directorio *MyApp* en el que hemos compilado la aplicación.</span><span class="sxs-lookup"><span data-stu-id="fc566-130">We're still working from the *MyApp* directory we built the app in.</span></span>

<span data-ttu-id="fc566-131">Abra *MyApp.csproj* en el editor de texto.</span><span class="sxs-lookup"><span data-stu-id="fc566-131">Open *MyApp.csproj* in your text editor.</span></span>

<span data-ttu-id="fc566-132">Después de ejecutar el comando [`dotnet add package`](../tools/dotnet-add-package.md), se agregan estas líneas al archivo de proyecto *MyApp.csproj*:</span><span class="sxs-lookup"><span data-stu-id="fc566-132">After running the [`dotnet add package`](../tools/dotnet-add-package.md) command, the following lines are added to your *MyApp.csproj* project file:</span></span>

 ```xml
 <ItemGroup>
    <PackageReference Include="Microsoft.XmlSerializer.Generator" Version="1.0.0" />
 </ItemGroup>
 ```

### <a name="add-another-itemgroup-section-for-net-core-cli-tool-support"></a><span data-ttu-id="fc566-133">Agregar otra sección ItemGroup para admitir la herramienta CLI de .NET Core</span><span class="sxs-lookup"><span data-stu-id="fc566-133">Add another ItemGroup section for .NET Core CLI Tool support</span></span>

<span data-ttu-id="fc566-134">Agregue estas líneas después de la sección `ItemGroup` que hemos inspeccionado:</span><span class="sxs-lookup"><span data-stu-id="fc566-134">Add the following lines after the `ItemGroup` section that we inspected:</span></span>

 ```xml
 <ItemGroup>
    <DotNetCliToolReference Include="Microsoft.XmlSerializer.Generator" Version="1.0.0" />
 </ItemGroup>
 ```

### <a name="add-a-class-in-the-application"></a><span data-ttu-id="fc566-135">Agregar una clase en la aplicación</span><span class="sxs-lookup"><span data-stu-id="fc566-135">Add a class in the application</span></span>

<span data-ttu-id="fc566-136">Abra *Program.cs* en el editor de texto.</span><span class="sxs-lookup"><span data-stu-id="fc566-136">Open *Program.cs* in your text editor.</span></span> <span data-ttu-id="fc566-137">Agregue la clase con el nombre *MyClass* en *Program.cs*.</span><span class="sxs-lookup"><span data-stu-id="fc566-137">Add the class named *MyClass* in *Program.cs*.</span></span>

```csharp
public class MyClass
{
   public int Value;
}
```

### <a name="create-an-xmlserializer-for-myclass"></a><span data-ttu-id="fc566-138">Crear un `XmlSerializer` para MyClass</span><span class="sxs-lookup"><span data-stu-id="fc566-138">Create an `XmlSerializer` for MyClass</span></span>

<span data-ttu-id="fc566-139">Agregue esta línea dentro de *Main* para crear un `XmlSerializer` para MyClass:</span><span class="sxs-lookup"><span data-stu-id="fc566-139">Add the following line inside *Main* to create an `XmlSerializer` for MyClass:</span></span>

```csharp
var serializer = new System.Xml.Serialization.XmlSerializer(typeof(MyClass));
```

### <a name="build-and-run-the-application"></a><span data-ttu-id="fc566-140">Compilar y ejecutar la aplicación</span><span class="sxs-lookup"><span data-stu-id="fc566-140">Build and run the application</span></span>

<span data-ttu-id="fc566-141">Seguimos en la carpeta *MyApp*, desde donde vamos a ejecutar la aplicación mediante [`dotnet run`](../tools/dotnet-run.md). Se carga automáticamente y usa los serializadores generados previamente en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="fc566-141">Still within the *MyApp* folder, run the application via [`dotnet run`](../tools/dotnet-run.md) and it automatically loads and uses the pre-generated serializers at run time.</span></span>

<span data-ttu-id="fc566-142">Escriba el siguiente comando en la ventana de consola:</span><span class="sxs-lookup"><span data-stu-id="fc566-142">Type the following command in your console window:</span></span>

```dotnetcli
dotnet run
```

> [!NOTE]
> <span data-ttu-id="fc566-143">[`dotnet run`](../tools/dotnet-run.md) llama a [`dotnet build`](../tools/dotnet-build.md) para asegurarse de que los destinos de la compilación se han creado y, después, llama a `dotnet <assembly.dll>` para ejecutar la aplicación de destino.</span><span class="sxs-lookup"><span data-stu-id="fc566-143">[`dotnet run`](../tools/dotnet-run.md) calls [`dotnet build`](../tools/dotnet-build.md) to ensure that the build targets have been built, and then calls `dotnet <assembly.dll>` to run the target application.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fc566-144">Los comandos y los pasos que se muestran en este tutorial para ejecutar la aplicación se usan solo durante el desarrollo.</span><span class="sxs-lookup"><span data-stu-id="fc566-144">The commands and steps shown in this tutorial to run your application are used during development time only.</span></span> <span data-ttu-id="fc566-145">Una vez que esté listo para implementar la aplicación, eche un vistazo a las diferentes [estrategias de implementación](../deploying/index.md) para aplicaciones .NET Core y al comando [`dotnet publish`](../tools/dotnet-publish.md).</span><span class="sxs-lookup"><span data-stu-id="fc566-145">Once you're ready to deploy your app, take a look at the different [deployment strategies](../deploying/index.md) for .NET Core apps and the [`dotnet publish`](../tools/dotnet-publish.md) command.</span></span>

<span data-ttu-id="fc566-146">Si todo se realiza correctamente, se genera un ensamblado con el nombre *.dll MyApp.XmlSerializers.dll* en la carpeta de salida.</span><span class="sxs-lookup"><span data-stu-id="fc566-146">If everything succeeds, an assembly named *MyApp.XmlSerializers.dll* is generated in the output folder.</span></span>

<span data-ttu-id="fc566-147">¡Enhorabuena!</span><span class="sxs-lookup"><span data-stu-id="fc566-147">Congratulations!</span></span> <span data-ttu-id="fc566-148">Acaba de:</span><span class="sxs-lookup"><span data-stu-id="fc566-148">You have just:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="fc566-149">Crear una aplicación .NET Core.</span><span class="sxs-lookup"><span data-stu-id="fc566-149">Created a .NET Core app.</span></span>
> - <span data-ttu-id="fc566-150">Agregar una referencia al paquete Microsoft.XmlSerializer.Generator.</span><span class="sxs-lookup"><span data-stu-id="fc566-150">Added a reference to the Microsoft.XmlSerializer.Generator package.</span></span>
> - <span data-ttu-id="fc566-151">Editar MyApp.csproj para agregar dependencias.</span><span class="sxs-lookup"><span data-stu-id="fc566-151">Edited your MyApp.csproj to add dependencies.</span></span>
> - <span data-ttu-id="fc566-152">Agregue una clase y un XmlSerializer.</span><span class="sxs-lookup"><span data-stu-id="fc566-152">Added a class and an XmlSerializer.</span></span>
> - <span data-ttu-id="fc566-153">Compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="fc566-153">Built and ran the application.</span></span>

## <a name="related-resources"></a><span data-ttu-id="fc566-154">Recursos relacionados</span><span class="sxs-lookup"><span data-stu-id="fc566-154">Related resources</span></span>

- [<span data-ttu-id="fc566-155">Introducción a la serialización XML</span><span class="sxs-lookup"><span data-stu-id="fc566-155">Introducing XML Serialization</span></span>](../../standard/serialization/introducing-xml-serialization.md)
- [<span data-ttu-id="fc566-156">Serialización con XmlSerializer (C#)</span><span class="sxs-lookup"><span data-stu-id="fc566-156">How to serialize using XmlSerializer (C#)</span></span>](../../standard/linq/serialize-xmlserializer.md)
- [<span data-ttu-id="fc566-157">Cómo: Serializar con XmlSerializer (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fc566-157">How to: Serialize Using XmlSerializer (Visual Basic)</span></span>](../../standard/linq/serialize-xmlserializer.md)
