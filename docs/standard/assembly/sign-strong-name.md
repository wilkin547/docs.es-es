---
title: Procedimiento para firmar un ensamblado con un nombre seguro
description: En este artículo se muestra cómo firmar un ensamblado .NET con un nombre seguro mediante la pestaña Firma, el enlazador de ensamblados, los atributos de ensamblado o las opciones del compilador.
ms.date: 08/20/2019
helpviewer_keywords:
- strong-named assemblies, signing with strong names
- signing assemblies
- assemblies [.NET Framework], signing
- assemblies [.NET Framework], strong-named
ms.assetid: 2c30799a-a826-46b4-a25d-c584027a6c67
dev_langs:
- csharp
- vb
- cpp
ms.openlocfilehash: d4888a12ac0494ca34eac3553a5374c3517fee38
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378615"
---
# <a name="how-to-sign-an-assembly-with-a-strong-name"></a>Procedimiento para firmar un ensamblado con un nombre seguro

> [!NOTE]
> Aunque .NET Core admite ensamblados con nombre seguro, y todos los ensamblados de la biblioteca .NET Core están firmados, la mayoría de los ensamblados de terceros no necesitan nombres seguros. Para obtener más información, consulte [Strong Name Signing (Firma con nombre seguro)](https://github.com/dotnet/runtime/blob/master/docs/project/strong-name-signing.md) en GitHub.

Existen varias formas de firmar un ensamblado con un nombre seguro:  
  
- Mediante la pestaña **Firma** del cuadro de diálogo **Propiedades** de un proyecto en Visual Studio. Esta es la forma más sencilla y cómoda de firmar un ensamblado con un nombre seguro.  
  
- Mediante el uso de [Assembly Linker (Al.exe)](../../framework/tools/al-exe-assembly-linker.md) para vincular un módulo de código de .NET Framework (un archivo *.netmodule*) a un archivo de claves.  
  
- Mediante el uso de atributos de ensamblado para insertar la información de nombre seguro en el código. Se puede usar el atributo <xref:System.Reflection.AssemblyKeyFileAttribute> o <xref:System.Reflection.AssemblyKeyNameAttribute> , dependiendo de dónde esté ubicado el archivo de claves que se va a utilizar.  
  
- Mediante el uso de opciones del compilador.  
  
 Es necesario disponer de un par de claves criptográficas para firmar un ensamblado con un nombre seguro. Para obtener más información sobre la creación de un par de claves, vea [Cómo: Crear un par de claves privada y pública](create-public-private-key-pair.md).  
  
## <a name="create-and-sign-an-assembly-with-a-strong-name-by-using-visual-studio"></a>Creación y firma de un ensamblado con un nombre seguro mediante el uso de Visual Studio  
  
1. En el **Explorador de soluciones**, abra el menú contextual del proyecto y luego elija **Propiedades**.  
  
2. Elija la pestaña **Firma** .  
  
3. Active la casilla **Firmar el ensamblado** .  
  
4. En la casilla **Elija un archivo de clave de nombre seguro**, elija **Examinar** y, a continuación, navegue hasta el archivo de claves. Para crear un nuevo archivo de claves, elija **Nuevo** y escriba su nombre en el cuadro de diálogo **Crear clave de nombre seguro**.  
  
> [!NOTE]
> Para [retrasar la firma de un ensamblado](delay-sign.md), elija un archivo de clave pública.  
  
### <a name="create-and-sign-an-assembly-with-a-strong-name-by-using-the-assembly-linker"></a>Creación y firma de un ensamblado con un nombre seguro mediante el uso de la herramienta Assembly Linker  
  
En [Símbolo del sistema para desarrolladores de Visual Studio](../../framework/tools/developer-command-prompt-for-vs.md), escriba el comando siguiente:  

**al** **/out:** \<*assemblyName*>  *\<moduleName>* **/keyfile:** \<*keyfileName*>  

Dónde:  

- *assemblyName* es el nombre del ensamblado seguro con firma (un archivo *.dll* o *.exe*) que emitirá la herramienta Assembly Linker.  
  
- *moduleName* es el nombre de un módulo de código de .NET Framework (un archivo *.netmodule*) que incluye uno o varios tipos. Puede crear un archivo *.netmodule* si compila el código con el modificador `/target:module` en C# o Visual Basic.
  
- *keyfileName* es el nombre del contenedor o del archivo que incluye el par de claves. Assembly Linker interpreta una ruta de acceso relativa en relación con el directorio actual.  

En el ejemplo siguiente se firma el ensamblado *MyAssembly.dll* con un nombre seguro mediante el uso del archivo de clave *sgKey.snk*.  

```console
al /out:MyAssembly.dll MyModule.netmodule /keyfile:sgKey.snk  
```  
  
Para obtener más información sobre esta herramienta, consulte el tema sobre [Assembly Linker](../../framework/tools/al-exe-assembly-linker.md).  
  
## <a name="sign-an-assembly-with-a-strong-name-by-using-attributes"></a>Firma de un ensamblado con un nombre seguro mediante el uso de atributos  
  
1. Agregue el atributo <xref:System.Reflection.AssemblyKeyFileAttribute?displayProperty=nameWithType> o <xref:System.Reflection.AssemblyKeyNameAttribute> al archivo de código fuente y especifique el nombre del archivo o contenedor donde se incluye el par de claves que se va a usar al firmar el ensamblado con un nombre seguro.  

2. Compile el archivo de código fuente normalmente.  

   > [!NOTE]
   > Los compiladores de C# y Visual Basic emiten advertencias del compilador (CS1699 y BC41008, respectivamente) cuando encuentran el atributo <xref:System.Reflection.AssemblyKeyFileAttribute> o <xref:System.Reflection.AssemblyKeyNameAttribute> en el código fuente. Las advertencias se pueden omitir.  

En el ejemplo siguiente se usa el atributo <xref:System.Reflection.AssemblyKeyFileAttribute> con un archivo de claves denominado *keyfile.snk*, que está ubicado en el directorio en el cual se compila el ensamblado.  

```cpp
[assembly:AssemblyKeyFileAttribute("keyfile.snk")];
```

```csharp
[assembly:AssemblyKeyFileAttribute("keyfile.snk")]
```

```vb
<Assembly:AssemblyKeyFileAttribute("keyfile.snk")>
```

También se puede retrasar la firma de un ensamblado al compilar el archivo de código fuente. Para obtener más información, vea [Retraso de la firma de un ensamblado](delay-sign.md).  

## <a name="sign-an-assembly-with-a-strong-name-by-using-the-compiler"></a>Firma de un ensamblado con un nombre seguro mediante el uso del compilador  

Compile el archivo o archivos de código fuente con la opción del compilador `/keyfile` o de `/delaysign` en C# y Visual Basic, o la opción del vinculador `/KEYFILE` o `/DELAYSIGN` en C++. Tras el nombre de la opción, agregue dos puntos y el nombre del archivo de claves. Si se usan compiladores de la línea de comandos, se puede copiar el archivo de claves en el directorio que contiene los archivos de código fuente.  

Para obtener información sobre la firma retardada, vea [Retraso de la firma de un ensamblado](delay-sign.md).  

En el ejemplo siguiente se usa el compilador de C# y se firma el ensamblado *UtilityLibrary.dll* con un nombre seguro mediante el archivo de claves *sgKey.snk*.  

```cmd
csc /t:library UtilityLibrary.cs /keyfile:sgKey.snk  
```  

## <a name="see-also"></a>Vea también

- [Creación y uso de ensamblados con nombre seguro](create-use-strong-named.md)
- [Cómo: Crear un par de claves privada y pública](create-public-private-key-pair.md)
- [Al.exe (Assembly Linker)](../../framework/tools/al-exe-assembly-linker.md)
- [Retraso de la firma de un ensamblado](delay-sign.md)
- [Administración de la firma de ensamblados y manifiestos](/visualstudio/ide/managing-assembly-and-manifest-signing)
- [Página Firma, Diseñador de proyectos](/visualstudio/ide/reference/signing-page-project-designer)
