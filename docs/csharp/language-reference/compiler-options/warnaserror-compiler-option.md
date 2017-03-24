---
title: "/warnaserror (C# Compiler Options) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "/warnaserror"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "/warnaserror compiler option [C#]"
  - "-warnaserror compiler option [C#]"
  - "warnaserror compiler option [C#]"
ms.assetid: 04680ec3-08d6-4e2e-a274-38310e10e33c
caps.latest.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 15
---
# /warnaserror (C# Compiler Options)
La opción **\/warnaserror\+** trata todas las advertencias como errores  
  
## Sintaxis  
  
```  
/warnaserror[<U>+</U> | -][:warning-list]  
```  
  
## Comentarios  
 Los mensajes que, normalmente, se mostrarían como advertencias se muestran como errores y el proceso de compilación se detiene \(no se compilan archivos de salida\).  
  
 De manera predeterminada, está activada la opción **\/warnaserror\-**, que hace que las advertencias no impidan la generación de un archivo de salida.  La opción **\/warnaserror**, que equivale a **\/warnaserror\+**, hace que se traten las advertencias como errores.  
  
 De manera optativa, si desea que sólo se traten como errores algunas advertencias concretas, puede especificar sus números en una lista separada por comas.  
  
 Utilice [\/warn](../../../csharp/language-reference/compiler-options/warn-compiler-option.md) para especificar el nivel de advertencia que debe mostrar el compilador.  Utilice [\/nowarn](../../../csharp/language-reference/compiler-options/nowarn-compiler-option.md) para deshabilitar determinadas advertencias.  
  
### Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio  
  
1.  Abra la página **Propiedades** del proyecto.  
  
2.  Haga clic en la página de propiedades **Compilar**.  
  
3.  Modifique el valor de la propiedad **Tratar advertencias como errores**.  
  
     Para establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.CSharpProjectConfigurationProperties3.TreatWarningsAsErrors%2A>.  
  
## Ejemplo  
 Para compilar `in.cs` y hacer que el compilador no muestre advertencias, ejecute:  
  
```  
csc /warnaserror in.cs  
csc /warnaserror:642,649,652 in.cs  
```  
  
## Vea también  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [Cómo: Modificar las propiedades y los valores de configuración del proyecto](http://msdn.microsoft.com/es-es/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)