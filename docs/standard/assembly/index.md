---
title: Ensamblados de .NET
ms.date: 07/10/2018
ms.assetid: 149f5ca5-5b34-4746-9542-1ae43b2d0256
---
# <a name="assemblies-in-net"></a>Ensamblados de .NET

Los ensamblados componen la unidad fundamental de implementación, control de versiones, reutilización, ámbito de activación y permisos de seguridad en una aplicación basada en .NET. Los ensamblados adoptan la forma de un archivo ejecutable (.exe) o de un archivo de biblioteca de vínculos dinámicos (.dll) y son bloques de compilación de aplicaciones .NET. Proporcionan a Common Language Runtime la información necesaria para conocer las implementaciones de tipos. Puede pensar en un ensamblado como si fuera una colección de tipos y recursos que forman una unidad lógica de funcionalidad y se compilan para funcionar en conjunto.

En .NET Core y .NET Framework, se puede crear un ensamblado a partir de uno o varios archivos de código fuente. En .NET Framework, los ensamblados pueden contener uno o varios módulos. Esto permite que los proyectos más grandes se planeen de forma que varios desarrolladores individuales trabajen en archivos de código fuente o módulos separados, que se combinan para crear un ensamblado único. Para más información sobre los módulos, vea el tema [Procedimiento para compilar de un ensamblado de varios archivos](../../framework/app-domains/how-to-build-a-multifile-assembly.md).

Los ensamblados tienen las propiedades siguientes:

- Los ensamblados son archivos .exe o .dll implementados.

- Para bibliotecas cuyo destino es .NET Framework, puede compartir un ensamblado entre aplicaciones colocándolo en la [memoria caché global de ensamblados](../../framework/app-domains/gac.md). Los ensamblados deben tener un nombre seguro antes de que se puedan incluir en la caché global de ensamblados. Para más información, vea [Ensamblados con nombre seguro](../../framework/app-domains/strong-named-assemblies.md).

- Los ensamblados solo se cargan en memoria si son necesarios. Si no se utilizan, no se cargan. Esto significa que los ensamblados pueden ser una manera eficaz de administrar recursos en proyectos más grandes.

- Mediante programación, puede obtener información sobre un ensamblado mediante reflexión. Para más información, vea [Reflexión (C#)](../../csharp/programming-guide/concepts/reflection.md) o [Reflexión (Visual Basic)](../../visual-basic/programming-guide/concepts/reflection.md).

- Puede cargar un ensamblado solo para inspeccionarlo mediante una llamada a un método <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom%2A?displayProperty=nameWithType>.

## <a name="assembly-manifest"></a>Manifiesto del ensamblado

Dentro de cada ensamblado hay un *manifiesto del ensamblado*. De forma similar a una tabla de contenido, el manifiesto del ensamblado contiene lo siguiente:

- La identidad del ensamblado (su nombre y versión).

- Una tabla de archivos que describe todos los demás archivos que componen el ensamblado, como cualquier otro ensamblado creado en que se basan los archivos .exe o .dll, o incluso archivos de mapa de bits o Léame.

- Una *lista de referencia de ensamblado*, que es una lista de todas las dependencias externas, archivos .dll u otros archivos que la aplicación necesita que alguien puede haber creado. Las referencias de ensamblado contienen referencias a objetos globales y privados. Los objetos globales están disponibles para todas las demás aplicaciones. En .NET Core, están acoplados con un determinado runtime de .NET Core. En .NET Framework, residen en la caché global de ensamblados. El espacio de nombres <xref:System.IO?displayProperty=nameWithType> es un ejemplo de un ensamblado en la caché global de ensamblados. Los objetos privados deben estar en un directorio del mismo nivel o debajo del directorio en el que se instala la aplicación.

Dado que los ensamblados contienen información sobre contenido, control de versiones y dependencias, las aplicaciones que los usan no confían en valores del Registro de Windows para funcionar correctamente. Los ensamblados reducen los conflictos de .dll y hacen las aplicaciones más confiables y fáciles de implementar. En muchos casos, puede instalar una aplicación basada en .NET con tan solo copiar sus archivos en el equipo de destino. Para más información, vea [Manifiesto del ensamblado](../../framework/app-domains/assembly-manifest.md).

## <a name="adding-a-reference-to-an-assembly"></a>Incorporación de una referencia a un ensamblado

Para usar un ensamblado, debe agregar una referencia a él. A continuación, puede usar la [directiva using](../../csharp/language-reference/keywords/using-directive.md) para C# o la [instrucción Imports](../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) para Visual Basic para elegir el espacio de nombres de los elementos que desea utilizar. Una vez que se hace referencia a un ensamblado y se importa, todos los tipos accesibles, propiedades, métodos y otros miembros de sus espacios de nombres están disponibles para la aplicación como si su código formara parte del archivo de origen.

> [!NOTE]
> La referencia a la mayoría de los ensamblados de la biblioteca de clases de .NET se hace automáticamente. En algunos casos, sin embargo, es posible que no se haga referencia automáticamente a un ensamblado del sistema. En .NET Core, puede agregar una referencia al paquete de NuGet que contiene el ensamblado, ya sea con el Administrador de paquetes de NuGet en Visual Studio o agregando un elemento [<PackageReference>](../../core/tools/dependencies.md#the-new-packagereference-element) para el ensamblado al proyecto *.csproj o *.vbproj. En .NET Framework, puede agregar una referencia al ensamblado mediante el cuadro de diálogo **Agregar referencia** de Visual Studio o mediante la opción de la línea de comandos `-reference` para los compiladores [C#](../../csharp/language-reference/compiler-options/reference-compiler-option.md) o [Visual Basic](../../visual-basic/reference/command-line-compiler/reference.md).

En C#, también puede usar dos versiones del mismo ensamblado en una sola aplicación. Para obtener más información, vea [alias externo](../../csharp/language-reference/keywords/extern-alias.md).

## <a name="creating-an-assembly"></a>Creación de un ensamblado

Compile la aplicación mediante Visual Studio, mediante la línea de comandos con herramientas de la interfaz de línea de comandos (CLI) de .NET Core o mediante ensamblados de .NET Framework con un compilador de línea de comandos. Para más información sobre la compilación de ensamblados mediante herramientas de la CLI de .NET, consulte [Herramientas de la interfaz de la línea de comandos (CLI) de .NET Core](../../core/tools/index.md). Para compilar ensamblados con los compiladores de línea de comandos, consulte [Compilar la línea de comandos con csc.exe](../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) para C# y [Compilar desde la línea de comandos (Visual Basic)](../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) para Visual Basic.

> [!NOTE]
> Para compilar un ensamblado en Visual Studio, en el menú **Compilar**, seleccione **Compilar**.

## <a name="see-also"></a>Vea también

- [Formato de archivo de ensamblado .NET](file-format.md)
- [Ensamblados en Common Language Runtime](../../framework/app-domains/assemblies-in-the-common-language-runtime.md)
- [Ensamblados de confianza](friend-assemblies.md)
- [Cómo: Cargar y descargar ensamblados (C#)](../../csharp/programming-guide/concepts/assemblies-gac/how-to-load-and-unload-assemblies.md)
- [Cómo: Carga y descarga de ensamblados (Visual Basic)](../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-load-and-unload-assemblies.md)
- [Cómo: Usar y depurar la descargabilidad de ensamblado en .NET Core](unloadability-howto.md)
- [Cómo: Determinar si un archivo es un ensamblado (C#)](../../csharp/programming-guide/concepts/assemblies-gac/how-to-determine-if-a-file-is-an-assembly.md)
- [Cómo: Determinar si un archivo es un ensamblado (Visual Basic)](../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-determine-if-a-file-is-an-assembly.md)
