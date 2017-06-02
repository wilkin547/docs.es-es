---
title: "C&#243;mo: Compilar un ensamblado de un solo archivo | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "ensamblados [.NET Framework], archivo único"
  - "manifiesto del ensamblado, ensamblados de un solo archivo"
  - "módulos de código"
  - "compiladores de línea de comandos"
  - "ensamblados de biblioteca"
  - "nombre de archivo de salida para ensamblados"
  - "ensamblados de un solo archivo"
ms.assetid: a6063221-43a5-4d3e-814c-288a4ec69aec
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# C&#243;mo: Compilar un ensamblado de un solo archivo
Un ensamblado de un único archivo, que es el tipo de ensamblado más sencillo, contiene la información e implementación del tipo, además del [manifiesto del ensamblado](../../../docs/framework/app-domains/assembly-manifest.md).  Para crear un ensamblado de un único archivo se pueden usar compiladores de la línea de comandos o [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)].  De forma predeterminada, el compilador crea un archivo de ensamblado con la extensión .exe.  
  
> [!NOTE]
>  [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] para C\# y Visual Basic solo se puede utilizar para crear ensamblados de un solo archivo.  Si se desea crear ensamblados de múltiples archivos, se deben usar compiladores de la línea de comandos o [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] para Visual C\+\+.  
  
 Los procedimientos siguientes muestran cómo se crean ensamblados de un único archivo mediante compiladores de la línea de comandos.  
  
### Para crear un ensamblado con la extensión .exe  
  
1.  En el símbolo del sistema, escriba el siguiente comando:  
  
     *\<nombre del módulo* *de*\> \<comando del compilador\>  
  
     En este comando, *comando del compilador* es el comando del compilador para el lenguaje utilizado en el módulo de código y *nombre del módulo* es el nombre del módulo de código que se va a compilar en el ensamblado.  
  
 En el ejemplo siguiente se crea un ensamblado denominado `myCode.exe` desde un módulo de código denominado `myCode`.  
  
```csharp  
csc myCode.cs  
```  
  
```vb  
vbc myCode.vb  
```  
  
#### Para crear un ensamblado con una extensión .exe y especificar el nombre del archivo de salida  
  
1.  En el símbolo del sistema, escriba el siguiente comando:  
  
     *\<nombre del módulo* *de*\> nombre de archivo de\<**\/out:** *de*\> \<comando del compilador\>  
  
     En este comando, *comando del compilador* es el comando del compilador para el lenguaje usado en el módulo de código, *nombre de archivo* es el nombre del archivo de salida y *nombre del módulo* es el nombre del módulo de código que se va a compilar en el ensamblado.  
  
 En el ejemplo siguiente se crea un ensamblado denominado `myAssembly.exe` desde un módulo de código denominado `myCode`.  
  
```csharp  
csc /out:myAssembly.exe myCode.cs  
```  
  
```vb  
vbc /out:myAssembly.exe myCode.vb  
```  
  
## Crear ensamblados de biblioteca  
 Un ensamblado de biblioteca es parecido a una biblioteca de clases.  Contiene tipos a los que harán referencia otros ensamblados, pero no tiene un punto de entrada para comenzar la ejecución.  
  
#### Para crear un ensamblado de biblioteca  
  
1.  En el símbolo del sistema, escriba el siguiente comando:  
  
     \<*comando del compilador*\>**\/t:library**\<*nombre del módulo*\>  
  
     En este comando, *comando del compilador* es el comando del compilador para el lenguaje utilizado en el módulo de código y *nombre del módulo* es el nombre del módulo de código que se va a compilar en el ensamblado.  También se pueden usar otras opciones de compilador, por ejemplo **\/out:**.  
  
 En el ejemplo siguiente se crea un ensamblado de biblioteca denominado `myCodeAssembly.dll` desde un módulo de código denominado `myCode`.  
  
```csharp  
csc /out:myCodeLibrary.dll /t:library myCode.cs  
```  
  
```vb  
vbc /out:myCodeLibrary.dll /t:library myCode.vb  
```  
  
## Vea también  
 [Crear ensamblados](../../../docs/framework/app-domains/create-assemblies.md)   
 [Ensamblados de varios archivos](../../../docs/framework/app-domains/multifile-assemblies.md)   
 [Cómo: Compilar un ensamblado de varios archivos](../../../docs/framework/app-domains/how-to-build-a-multifile-assembly.md)   
 [Programar con ensamblados](../../../docs/framework/app-domains/programming-with-assemblies.md)