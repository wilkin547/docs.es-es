---
title: "/platform (C# Compiler Options) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "/platform"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "platform compiler option [C#]"
  - "-platform compiler option [C#]"
  - "/platform compiler option [C#]"
ms.assetid: c290ff5e-47f4-4a85-9bb3-9c2525b0be04
caps.latest.revision: 46
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 46
---
# /platform (C# Compiler Options)
Especifica qué versión de Common Language Runtime \(CLR\) puede ejecutar el ensamblado.  
  
## Sintaxis  
  
```  
/platform:string  
```  
  
#### Parámetros  
 `string`  
 anycpu \(valor predeterminado\), anycpu32bitpreferred, la ARM, x64, x86, o Itanium.  
  
## Comentarios  
  
-   **anycpu** \(predeterminado\) compila el ensamblado para ejecutarse en cualquier plataforma.  La aplicación se ejecuta como un proceso de 64 bits siempre que sea posible y vuelve a 32 bits cuando sólo ese modo está disponible.  
  
-   **anycpu32bitpreferred** compila en ensamblado de forma que se pueda ejecutar en cualquier plataforma.  La aplicación se ejecuta en modo de 32 bits en sistemas que admiten aplicaciones de 64 bits y de 32 bits.  Puede especificar esta opción solamente para los proyectos destinados a .NET Framework 4,5.  
  
-   **ARM** compila el ensamblado para ejecutarse en un equipo que tenga un procesador de \(ARM\) de equipo de la Computación avanzada RISC.  
  
-   **x64** compila el ensamblado que se ejecuta por Common Language Runtime 64 bits en un equipo que admite el conjunto de instrucciones AMD64 o EM64T.  
  
-   **x86** compila el ensamblado que se ejecuta por el de 32 bits, Common Language Runtime de x86\-compatible.  
  
-   **Itanium** compila el ensamblado que se ejecuta por Common Language Runtime de 64 bits en un equipo con un procesador Itanium.  
  
 En un sistema operativo Windows de 64 bits:  
  
-   Los ensamblados compiladas con **\/platform:x86** se ejecutan en el CLR de 32 bits que se ejecuta bajo WOW64.  
  
-   Un archivo DLL compilado con **\/platform:anycpu** se ejecuta en el CLR que el proceso en el que se carga.  
  
-   Ejecutables que se compilan con **\/platform:anycpu** se ejecutan en el CLR de 64 bits.  
  
-   Ejecutables compiladas con **\/platform:anycpu32bitpreferred** se ejecutan en el CLR de 32 bits.  
  
 El establecimiento de **anycpu32bitpreferred** solo es válido para los archivos ejecutables \(.EXE\), y requiere .NET Framework 4,5.  
  
 Para más información sobre cómo desarrollar una aplicación que se ejecute en un sistema operativo Windows de 64 bits, vea [Aplicaciones de 64 bits](../Topic/64-bit%20Applications.md).  
  
### Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio  
  
1.  Abra la página **Propiedades** del proyecto.  
  
2.  Haga clic en la página de propiedades **Compilar**.  
  
3.  Modifique la propiedad de **Destino de la plataforma** y, para los proyectos destinados a.NET Framework 4,5, active o desactive la casilla de **Preferencia de 32 bits** .  
  
 **Nota**  
 **\/platform** no está disponible en el entorno de desarrollo de Visual C\# Express.  
  
 Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.CSharpProjectConfigurationProperties3.PlatformTarget%2A>.  
  
## Ejemplo  
 El ejemplo siguiente se muestra cómo utilizar la opción de **\/platform** de especificar que la aplicación se debe ejecutar por el CLR de 64 bits en un sistema operativo Windows de 64 bits.  
  
```  
csc /platform:anycpu filename.cs  
```  
  
## Vea también  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [Cómo: Modificar las propiedades y los valores de configuración del proyecto](http://msdn.microsoft.com/es-es/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)