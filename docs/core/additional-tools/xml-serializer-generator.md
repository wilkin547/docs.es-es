---
title: Generador de serializador XML de Microsoft
description: Información general sobre el generador de serializador XML de Microsoft. Use el generador de serializador XML para generar un ensamblado de serialización XML para los tipos contenidos en el proyecto.
author: mlacouture
ms.date: 01/19/2017
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 094dd1227033e167050ad73121b3005a592a0ae4
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714519"
---
# <a name="using-microsoft-xml-serializer-generator-on-net-core"></a>Usar el generador de serializador XML de Microsoft en .NET Core

Este tutorial muestra cómo usar el generador de serializador XML de Microsoft en una aplicación .NET Core de C#. Este tutorial ayuda a:

> [!div class="checklist"]
>
> - Cómo crear una aplicación .NET Core
> - Cómo agregar una referencia al paquete Microsoft.XmlSerializer.Generator
> - Cómo editar MyApp.csproj para agregar dependencias
> - Cómo agregar una clase y un XmlSerializer
> - Cómo compilar y ejecutar la aplicación

Tal y como sucede con el [generador de serializador de XML (sgen.exe)](../../standard/serialization/xml-serializer-generator-tool-sgen-exe.md) para .NET Framework, el [paquete Microsoft.XmlSerializer.Generator de NuGet ](https://www.nuget.org/packages/Microsoft.XmlSerializer.Generator) es el equivalente para proyectos de .NET Core y .NET Standard. Crea un ensamblado de serialización de XML para los tipos contenidos en un ensamblado para mejorar el rendimiento de inicio de la serialización XML al serializar o deserializar objetos de esos tipos con <xref:System.Xml.Serialization.XmlSerializer>.

## <a name="prerequisites"></a>Requisitos previos

Para realizar este tutorial:

- [SDK de .NET Core 2.1](https://dotnet.microsoft.com/download) o versiones posteriores.
- Su editor de código favorito.

> [!TIP]
> ¿Es necesario instalar un editor de código? Pruebe [Visual Studio](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocs).

## <a name="use-microsoft-xml-serializer-generator-in-a-net-core-console-application"></a>Usar el generador de serializador de XML de Microsoft en una aplicación de consola .NET Core

Las instrucciones siguientes muestran cómo usar el generador de serializador XML en una aplicación de consola .NET Core.

### <a name="create-a-net-core-console-application"></a>Creación de una aplicación de consola .NET Core

Abra un símbolo del sistema y cree una carpeta denominada *MyApp*. Vaya a la carpeta que creó y escriba estos comandos:

```dotnetcli
dotnet new console
```

### <a name="add-a-reference-to-the-microsoftxmlserializergenerator-package-in-the-myapp-project"></a>Agregue una referencia al paquete Microsoft.XmlSerializer.Generator en el proyecto de MyApp

Use el comando [`dotnet add package`](../tools//dotnet-add-package.md) para agregar la referencia en el proyecto.

Tipo:

```dotnetcli
dotnet add package Microsoft.XmlSerializer.Generator -v 1.0.0
```

### <a name="verify-changes-to-myappcsproj-after-adding-the-package"></a>Comprobar los cambios en MyApp.csproj después de agregar el paquete

Abra el editor de código para empezar. Todavía estamos trabajando desde el directorio *MyApp* en el que hemos compilado la aplicación.

Abra *MyApp.csproj* en el editor de texto.

Después de ejecutar el comando [`dotnet add package`](../tools//dotnet-add-package.md), se agregan estas líneas al archivo de proyecto *MyApp.csproj*:

 ```xml
 <ItemGroup>
    <PackageReference Include="Microsoft.XmlSerializer.Generator" Version="1.0.0" />
 </ItemGroup>
 ```

### <a name="add-another-itemgroup-section-for-net-core-cli-tool-support"></a>Agregar otra sección ItemGroup para admitir la herramienta CLI de .NET Core

Agregue estas líneas después de la sección `ItemGroup` que hemos inspeccionado:

 ```xml
 <ItemGroup>
    <DotNetCliToolReference Include="Microsoft.XmlSerializer.Generator" Version="1.0.0" />
 </ItemGroup>
 ```

### <a name="add-a-class-in-the-application"></a>Agregar una clase en la aplicación

Abra *Program.cs* en el editor de texto. Agregue la clase con el nombre *MyClass* en *Program.cs*.

```csharp
public class MyClass
{
   public int Value;
}
```

### <a name="create-an-xmlserializer-for-myclass"></a>Crear un `XmlSerializer` para MyClass

Agregue esta línea dentro de *Main* para crear un `XmlSerializer` para MyClass:

```csharp
var serializer = new System.Xml.Serialization.XmlSerializer(typeof(MyClass));
```

### <a name="build-and-run-the-application"></a>Compilar y ejecutar la aplicación

Seguimos en la carpeta *MyApp*, desde donde vamos a ejecutar la aplicación a través de [`dotnet run`](../tools/dotnet-run.md). Se carga automáticamente y usa los serializadores generados previamente en tiempo de ejecución.

Escriba el siguiente comando en la ventana de consola:

```dotnetcli
dotnet run
```

> [!NOTE]
> [`dotnet run`](../tools/dotnet-run.md) llama a [`dotnet build`](../tools/dotnet-build.md) para asegurarse de que los destinos de la compilación se han creado y, después, llama a `dotnet <assembly.dll>` para ejecutar la aplicación de destino.

> [!IMPORTANT]
> Los comandos y los pasos que se muestran en este tutorial para ejecutar la aplicación se usan solo durante el desarrollo. Una vez que esté listo para implementar la aplicación, eche un vistazo a las diferentes [estrategias de implementación](../deploying/index.md) para aplicaciones .NET Core y al comando [`dotnet publish`](../tools/dotnet-publish.md).

Si todo se realiza correctamente, se genera un ensamblado con el nombre *.dll MyApp.XmlSerializers.dll* en la carpeta de salida.

¡Enhorabuena! Acaba de:
> [!div class="checklist"]
>
> - Crear una aplicación .NET Core.
> - Agregar una referencia al paquete Microsoft.XmlSerializer.Generator.
> - Editar MyApp.csproj para agregar dependencias.
> - Agregue una clase y un XmlSerializer.
> - Compilar y ejecutar la aplicación.

## <a name="related-resources"></a>Recursos relacionados

- [Introducción a la serialización XML](../../standard/serialization/introducing-xml-serialization.md)
- [Serialización con XmlSerializer (C#)](../../csharp/programming-guide/concepts/linq/how-to-serialize-using-xmlserializer.md)
- [Cómo: Serializar con XmlSerializer (Visual Basic)](../../visual-basic/programming-guide/concepts/linq/how-to-serialize-using-xmlserializer.md)
