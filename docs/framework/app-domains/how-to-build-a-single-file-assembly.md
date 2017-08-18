---
title: "Cómo: Compilar un ensamblado de un solo archivo"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- assembly manifest, single-file assemblies
- library assemblies
- command-line compilers
- assemblies [.NET Framework], single-file
- output file name for assemblies
- code modules
- single-file assemblies
ms.assetid: a6063221-43a5-4d3e-814c-288a4ec69aec
caps.latest.revision: 10
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 1a584e6ded79489e5e33b07d02dde618541c6cc8
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-build-a-single-file-assembly"></a>Cómo: Compilar un ensamblado de un solo archivo
Un ensamblado de único archivo, que es el tipo de ensamblado más sencillo, contiene información y la implementación del tipo, así como el [manifiesto del ensamblado](../../../docs/framework/app-domains/assembly-manifest.md). Puede usar los compiladores de la línea de comandos o [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] para crear un ensamblado de único archivo. De forma predeterminada, el compilador crea un archivo de ensamblado con la extensión .exe.  
  
> [!NOTE]
>  [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] para C# y Visual Basic solo se puede usar para crear ensamblados de único archivo. Si desea crear ensamblados de múltiples archivos, debe usar compiladores de la línea de comandos o [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] para Visual C++.  
  
 En los procedimientos siguientes se muestra cómo crear ensamblados de único archivo mediante los compiladores de la línea de comandos.  
  
### <a name="to-create-an-assembly-with-an-exe-extension"></a>Para crear un ensamblado con una extensión .exe  
  
1.  En el símbolo del sistema, escriba el siguiente comando:  
  
     \<*comando del compilador*> \<*nombre del módulo*>  
  
     En este comando, *comando de compilador* es el comando del compilador del lenguaje usado en el módulo del código, mientras que *nombre del módulo* es el nombre del módulo del código al compilarlo en el ensamblado.  
  
 En el ejemplo siguiente se crea un ensamblado llamado `myCode.exe` desde un módulo de código llamado `myCode`.  
  
```csharp  
csc myCode.cs  
```  
  
```vb  
vbc myCode.vb  
```  
  
#### <a name="to-create-an-assembly-with-an-exe-extension-and-specify-the-output-file-name"></a>Para crear un ensamblado con la extensión .exe y especificar el nombre de archivo de salida  
  
1.  En el símbolo del sistema, escriba el siguiente comando:  
  
     \<*comando del compilador*> **/out:**\<*nombre del archivo*> \<*nombre del módulo*>  
  
     En este comando, *comando del compilador* es el comando del compilador del lenguaje usado en el módulo del código, *nombre del archivo* es el nombre del archivo de salida y *nombre del módulo* es el nombre del módulo del código al compilarlo en el ensamblado.  
  
 En el ejemplo siguiente se crea un ensamblado llamado `myAssembly.exe` desde un módulo de código llamado `myCode`.  
  
```csharp  
csc /out:myAssembly.exe myCode.cs  
```  
  
```vb  
vbc /out:myAssembly.exe myCode.vb  
```  
  
## <a name="creating-library-assemblies"></a>Crear ensamblados de biblioteca  
 Los ensamblados de biblioteca se parecen a las bibliotecas de clases. Contiene tipos a los que harán referencia otros ensamblados, pero no tiene ningún punto de entrada para comenzar la ejecución.  
  
#### <a name="to-create-a-library-assembly"></a>Para crear un ensamblado de biblioteca  
  
1.  En el símbolo del sistema, escriba el siguiente comando:  
  
     \<*comando del compilador*> **/t:library** \<*nombre del módulo*>  
  
     En este comando, *comando de compilador* es el comando del compilador del lenguaje usado en el módulo del código, mientras que *nombre del módulo* es el nombre del módulo del código al compilarlo en el ensamblado. También puede usar otras opciones del compilador, como la opción **/out:**.  
  
 En el ejemplo siguiente se crea un ensamblado de biblioteca llamado `myCodeAssembly.dll` desde un módulo de código llamado `myCode`.  
  
```csharp  
csc /out:myCodeLibrary.dll /t:library myCode.cs  
```  
  
```vb  
vbc /out:myCodeLibrary.dll /t:library myCode.vb  
```  
  
## <a name="see-also"></a>Vea también  
 [Creación de ensamblados](../../../docs/framework/app-domains/create-assemblies.md)   
 [Ensamblados de múltiples archivos](../../../docs/framework/app-domains/multifile-assemblies.md)   
 [Cómo: Compilar un ensamblado de varios archivos](../../../docs/framework/app-domains/how-to-build-a-multifile-assembly.md)   
 [Programar con ensamblados](../../../docs/framework/app-domains/programming-with-assemblies.md)

