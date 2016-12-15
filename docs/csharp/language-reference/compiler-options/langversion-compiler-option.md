---
title: "/langversion (C# Compiler Options) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/langversion"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "/langversion compiler option [C#]"
  - "-langversion compiler option [C#]"
  - "langversion compiler option [C#]"
ms.assetid: 3fb00b05-a0ff-4782-b313-13a4c0f62d94
caps.latest.revision: 33
caps.handback.revision: 33
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# /langversion (C# Compiler Options)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Hace que el compilador acepte solo la sintaxis incluida en la especificación del lenguaje C\# elegida.  
  
## Sintaxis  
  
```  
/langversion:option  
```  
  
## Argumentos  
 `option`  
 Valores válidos son:  
  
|Opción|Significado|  
|------------|-----------------|  
|default|El compilador acepta toda la sintaxis del lenguaje válida.|  
|ISO\-1|El compilador acepta solo la sintaxis incluida en la especificación del lenguaje C\# ISO\/CEI 23270:2003.|  
|ISO\-2|El compilador acepta solo la sintaxis incluida en la especificación del lenguaje C\# ISO\/CEI 23270:2006.  Esta especificación está disponible en [ISO](http://go.microsoft.com/fwlink/?LinkId=144406) el sitio Web.|  
|3|El compilador sólo acepta la sintaxis incluida en la versión 3.0 [Especificación del lenguaje C\#](../../../csharp/language-reference/language-specification.md).|  
  
## Comentarios  
 Los metadatos a los que hace referencia una aplicación de C\# no están sujetos a la opción del compilador **\/langversion**.  
  
 Dado que todas las versiones del compilador de C\# contienen extensiones que corresponden a la especificación del lenguaje, **\/langversion** no proporciona una funcionalidad equivalente a la de una versión anterior del compilador.  
  
 Sin tener en cuenta la configuración de **\/langversion** que utilice, debe emplear la versión actual de Common Language Runtime para crear archivos .exe o .dll.  Una excepción son los ensamblados de confianza y [\/moduleassemblyname \(Specify Friend Assembly for Module\)](../../../csharp/language-reference/compiler-options/moduleassemblyname-compiler-option.md), que funcionan bajo **\/langversion:ISO\-1**.  
  
### Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio  
  
1.  Abra la página **Propiedades** del proyecto.  
  
2.  Haga clic en la página de propiedades **Compilar**.  
  
3.  Haga clic en el botón **Avanzada**.  
  
4.  Modifique la propiedad **Versión del lenguaje**.  
  
 Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.CSharpProjectConfigurationProperties3.LanguageVersion%2A>.  
  
## Vea también  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [Cómo: Modificar las propiedades y los valores de configuración del proyecto](http://msdn.microsoft.com/es-es/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)   
 [Especificación del lenguaje C\#](../../../csharp/language-reference/language-specification.md)