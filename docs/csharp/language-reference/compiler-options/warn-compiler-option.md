---
title: "/warn (C# Compiler Options) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "/warn"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "warning level [C#]"
  - "/w compiler option [C#]"
  - "-w compiler option [C#]"
  - "-warn compiler option [C#]"
  - "/warn compiler option [C#]"
  - "w compiler option [C#]"
  - "warn compiler option [C#]"
ms.assetid: 5f80ff59-4991-4382-9f9a-77da18446e71
caps.latest.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 17
---
# /warn (C# Compiler Options)
La opción **\/warn** especifica el nivel de advertencia que debe mostrar el compilador.  
  
## Sintaxis  
  
```  
/warn:option  
```  
  
## Argumentos  
 `option`  
 El nivel de advertencia que se desea mostrar para la compilación: los números más bajos muestran sólo las advertencias muy graves; los números altos, más advertencias.  Los valores válidos están comprendidos entre 0 y 4:  
  
|Nivel de advertencia|Significado|  
|--------------------------|-----------------|  
|0|Desactiva la emisión de todos los mensajes de advertencia.|  
|1|Muestra los mensajes de advertencia graves.|  
|2|Muestra las advertencias de nivel 1 y también algunas otras menos graves, como las relativas a la ocultación de miembros de clase.|  
|3|Muestra las advertencias de nivel 2 y también algunas otras menos graves, como las relativas a expresiones que siempre se evalúan como `true` o `false`.|  
|4 \(valor predeterminado\)|Muestra todas las advertencias de nivel 3 y también las informativas.|  
  
## Comentarios  
 Para obtener información sobre un error o una advertencia, puede buscar su código en el índice de la Ayuda.  Encontrará otras formas de obtener información sobre errores o advertencias en [C\# Compiler Errors](../../../csharp/language-reference/compiler-messages/index.md).  
  
 Si desea tratar todas las advertencias como errores, utilice [\/warnaserror](../../../csharp/language-reference/compiler-options/warnaserror-compiler-option.md).  Utilice [\/nowarn](../../../csharp/language-reference/compiler-options/nowarn-compiler-option.md) para deshabilitar determinadas advertencias.  
  
 **\/w** es la forma abreviada de **\/warn**.  
  
### Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio  
  
1.  Abra la página **Propiedades** del proyecto.  
  
2.  Haga clic en la página de propiedades **Compilar**.  
  
3.  Modifique la propiedad **Nivel de advertencia**.  
  
 Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.CSharpProjectConfigurationProperties3.WarningLevel%2A>.  
  
## Ejemplo  
 Para compilar `in.cs` y hacer que el compilador sólo muestre las advertencias de nivel 1, ejecute:  
  
```  
csc /warn:1 in.cs  
```  
  
## Vea también  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [Cómo: Modificar las propiedades y los valores de configuración del proyecto](http://msdn.microsoft.com/es-es/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)