---
title: Procedimiento Firma de un ensamblado con un nombre seguro
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- strong-named assemblies, signing with strong names
- signing assemblies
- assemblies [.NET Framework], signing
- assemblies [.NET Framework], strong-named
ms.assetid: 2c30799a-a826-46b4-a25d-c584027a6c67
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5580b6d8af7319397ad7eb6416941c2be0dcdb76
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59303438"
---
# <a name="how-to-sign-an-assembly-with-a-strong-name"></a>Procedimiento Firma de un ensamblado con un nombre seguro
Existen varias formas de firmar un ensamblado con un nombre seguro:  
  
-   Mediante la pestaña **Firma** del cuadro de diálogo **Propiedades** de un proyecto en Visual Studio. Esta es la forma más sencilla y cómoda de firmar un ensamblado con un nombre seguro.  
  
-   Mediante el uso de [Assembly Linker (Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md) para vincular un módulo de código de .NET Framework (un archivo .netmodule) a un archivo de claves.  
  
-   Mediante el uso de atributos de ensamblado para insertar la información de nombre seguro en el código. Se puede usar el atributo <xref:System.Reflection.AssemblyKeyFileAttribute> o <xref:System.Reflection.AssemblyKeyNameAttribute> , dependiendo de dónde esté ubicado el archivo de claves que se va a utilizar.  
  
-   Mediante el uso de opciones del compilador.  
  
 Es necesario disponer de un par de claves criptográficas para firmar un ensamblado con un nombre seguro. Para obtener más información sobre la creación de un par de claves, vea [Cómo: Creación de un par de claves privada y pública](../../../docs/framework/app-domains/how-to-create-a-public-private-key-pair.md).  
  
### <a name="to-create-and-sign-an-assembly-with-a-strong-name-by-using-visual-studio"></a>Para crear y firmar un ensamblado con un nombre seguro utilizando Visual Studio  
  
1. En el **Explorador de soluciones**, abra el menú contextual del proyecto y luego elija **Propiedades**.  
  
2. Elija la pestaña **Firma** .  
  
3. Active la casilla **Firmar el ensamblado** .  
  
4. En la casilla **Elija un archivo de clave de nombre seguro**, elija **\<Examinar...>** y, a continuación, navegue hasta el archivo de claves. Para crear un nuevo archivo de claves, elija **\<Nuevo...>** y escriba su nombre en el cuadro de diálogo **Crear clave de nombre seguro**.  
  
> [!NOTE]
>  Para [retrasar la firma de un ensamblado](../../../docs/framework/app-domains/delay-sign-assembly.md), elija un archivo de clave pública.  
  
### <a name="to-create-and-sign-an-assembly-with-a-strong-name-by-using-the-assembly-linker"></a>Para crear y firmar un ensamblado con un nombre seguro utilizando la herramienta Assembly Linker  
  
-   En [Símbolo del sistema para desarrolladores de Visual Studio](../../../docs/framework/tools/developer-command-prompt-for-vs.md), escriba el comando siguiente:  
  
     **al** **/out:**\<*assemblyName*> *\<moduleName>* **/keyfile:**\<*keyfileName*>  
  
     donde:  
  
     *assemblyName*  
     Nombre del ensamblado firmado seguro (archivo .dll o .exe) que la herramienta Assembly Linker emitirá.  
  
     *moduleName*  
     Nombre de un módulo de código de .NET Framework (un archivo .netmodule) que incluye uno o varios tipos. Puede crear un archivo .netmodule si compila el código con el modificador `/target:module` en C# o Visual Basic.  
  
     *keyfileName*  
     Nombre del contenedor o archivo que incluye el par de claves. Assembly Linker interpreta una ruta de acceso relativa en relación con el directorio actual.  
  
 En el ejemplo siguiente se firma el ensamblado `MyAssembly.dll` con un nombre seguro utilizando el archivo de clave `sgKey.snk`.  
  
```  
al /out:MyAssembly.dll MyModule.netmodule /keyfile:sgKey.snk  
```  
  
 Para obtener más información sobre esta herramienta, consulte el tema sobre [Assembly Linker](../../../docs/framework/tools/al-exe-assembly-linker.md).  
  
#### <a name="to-sign-an-assembly-with-a-strong-name-by-using-attributes"></a>Para firmar un ensamblado con un nombre seguro utilizando atributos  
  
1. Agregue el atributo <xref:System.Reflection.AssemblyKeyFileAttribute?displayProperty=nameWithType> o <xref:System.Reflection.AssemblyKeyNameAttribute> al archivo de código fuente y especifique el nombre del archivo o contenedor donde se incluye el par de claves que se va a usar al firmar el ensamblado con un nombre seguro.  
  
2. Compile el archivo de código fuente normalmente.  
  
> [!NOTE]
>  Los compiladores de C# y Visual Basic emiten advertencias del compilador (CS1699 y BC41008, respectivamente) cuando encuentran el atributo <xref:System.Reflection.AssemblyKeyFileAttribute> o <xref:System.Reflection.AssemblyKeyNameAttribute> en el código fuente. Las advertencias se pueden omitir.  
  
 En el ejemplo siguiente se usa el atributo <xref:System.Reflection.AssemblyKeyFileAttribute> con un archivo de claves denominado `keyfile.snk`, ubicado en el directorio en el que se compila el ensamblado.  
  
 [!code-cpp[AssemblyName_KeyPair#21](../../../samples/snippets/cpp/VS_Snippets_CLR/AssemblyName_KeyPair/CPP/keyfileattrib.cpp#21)]
 [!code-csharp[AssemblyName_KeyPair#21](../../../samples/snippets/csharp/VS_Snippets_CLR/AssemblyName_KeyPair/CS/keyfileattrib.cs#21)]
 [!code-vb[AssemblyName_KeyPair#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AssemblyName_KeyPair/VB/keyfileattrib.vb#21)]  
  
 También se puede retrasar la firma de un ensamblado al compilar el archivo de código fuente. Para obtener más información, vea [Retrasar la firma de un ensamblado](../../../docs/framework/app-domains/delay-sign-assembly.md).  
  
### <a name="to-sign-an-assembly-with-a-strong-name-by-using-the-compiler"></a>Para firmar un ensamblado con un nombre seguro utilizando el compilador  
  
-   Compile el archivo o archivos de código fuente con la opción del compilador `/keyfile` o de `/delaysign` en C# y Visual Basic, o la opción del vinculador `/KEYFILE` o `/DELAYSIGN` en C++. Tras el nombre de la opción, agregue dos puntos y el nombre del archivo de claves. Si se usan compiladores de la línea de comandos, se puede copiar el archivo de claves en el directorio que contiene los archivos de código fuente.  
  
     Para obtener información sobre la firma retardada, vea [Delay Signing an Assembly](../../../docs/framework/app-domains/delay-sign-assembly.md).  
  
     En el ejemplo siguiente se usa el compilador de C# y se firma el ensamblado `UtilityLibrary.dll` con un nombre seguro mediante el archivo de claves `sgKey.snk`.  
  
    ```  
    csc /t:library UtilityLibrary.cs /keyfile:sgKey.snk  
    ```  
  
## <a name="see-also"></a>Vea también

- [Crear y utilizar ensamblados con nombre seguro](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md)
- [Cómo: Creación de un par de claves privada y pública](../../../docs/framework/app-domains/how-to-create-a-public-private-key-pair.md)
- [Al.exe (Assembly Linker)](../../../docs/framework/tools/al-exe-assembly-linker.md)
- [Retrasar la firma de un ensamblado](../../../docs/framework/app-domains/delay-sign-assembly.md)
- [Administrar la firma de ensamblados y manifiestos](/visualstudio/ide/managing-assembly-and-manifest-signing)
- [Página Firma, Diseñador de proyectos](/visualstudio/ide/reference/signing-page-project-designer)
