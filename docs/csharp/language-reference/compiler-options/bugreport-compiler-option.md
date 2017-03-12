---
title: "/bugreport (C# Compiler Options) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "/bugreport"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "/bugreport compiler option [C#]"
  - "-bugreport compiler option [C#]"
  - "bugreport compiler option [C#]"
ms.assetid: f39665e3-4f6f-4357-88a2-3274c7bec0c1
caps.latest.revision: 20
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 20
---
# /bugreport (C# Compiler Options)
Especifica que la información de depuración se debe colocar en un archivo para un análisis posterior.  
  
## Sintaxis  
  
```  
/bugreport:file  
```  
  
## Argumentos  
 `file`  
 Nombre del archivo que va a contener el informe de error.  
  
## Comentarios  
 La opción **\/bugreport** especifica que la siguiente información se debe colocar en `file`:  
  
-   Una copia de todos los archivos de código fuente de la compilación.  
  
-   Una lista de las opciones del compilador utilizadas en la compilación.  
  
-   Información de versión acerca del compilador, el motor en tiempo de ejecución y el sistema operativo.  
  
-   Los ensamblados y módulos a los que se hace referencia \(guardados como dígitos hexadecimales\), excepto los ensamblados que se distribuyen con .NET Framework y el SDK.  
  
-   Resultados del compilador, si existen.  
  
-   Descripción del problema, que debe rellenar el usuario.  
  
-   Descripción de cómo se debería resolver el problema, que debe rellenar el usuario.  
  
 Si se utiliza esta opción con **\/errorreport:prompt** o **\/errorreport:send**, se enviará la información del archivo a Microsoft Corporation.  
  
 Puesto que se colocará una copia de todos los archivos de código fuente en `file`, es recomendable reproducir el defecto de código que se sospecha en el programa más corto posible.  
  
 Esta opción del compilador no está disponible en Visual Studio y no se puede cambiar mediante programación.  
  
 Observe que el contenido del archivo generado expone código fuente que podría producir la revelación inadvertida de información.  
  
## Vea también  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [\/errorreport \(Set Error Reporting Behavior\)](../../../csharp/language-reference/compiler-options/errorreport-compiler-option.md)   
 [Cómo: Modificar las propiedades y los valores de configuración del proyecto](http://msdn.microsoft.com/es-es/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)