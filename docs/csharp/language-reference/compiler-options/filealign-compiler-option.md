---
title: "/filealign (C# Compiler Options) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "/filealign"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "/alignment compiler option [C#]"
  - "filealign compiler option [C#]"
  - "-filealign compiler option [C#]"
  - "/sections compiler option [C#]"
  - "alignment compiler option [C#]"
  - "sections compiler option [C#]"
  - "-sections compiler option [C#]"
  - "/filealign compiler option [C#]"
  - "file sharing [C#]"
  - "-alignment compiler option [C#]"
  - "section alignment [C#]"
ms.assetid: 15cf1c98-3798-4ced-9f08-60619308a073
caps.latest.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 14
---
# /filealign (C# Compiler Options)
La opción **\/filealign** permite especificar el tamaño de las secciones del archivo de salida.  
  
## Sintaxis  
  
```  
/filealign:number  
```  
  
## Argumentos  
 `number`  
 Valor que especifica el tamaño de las secciones del archivo de salida.  Los valores válidos son 512, 1024, 2048, 4096 y 8192.  Estos valores se miden en bytes.  
  
## Comentarios  
 Cada sección se alineará con un límite que es múltiplo del valor **\/filealign**.  No hay un valor predeterminado fijo.  Si no se especifica **\/filealign**, Common Language Runtime elige un valor predeterminado en tiempo de compilación.  
  
 Especificar el tamaño de la sección afecta al tamaño del archivo de salida.  Puede ser útil modificar el tamaño de sección para programas que se ejecuten en dispositivos más pequeños.  
  
 Utilice [DUMPBIN](/visual-cpp/build/reference/dumpbin-options) para ver información acerca de las secciones del archivo de salida.  
  
### Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio  
  
1.  Abra la página **Propiedades** del proyecto.  
  
2.  Haga clic en la página de propiedades **Compilar**.  
  
3.  Haga clic en el botón **Avanzada**.  
  
4.  Modifique la propiedad **Alineación de archivo**.  
  
 Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.CSharpProjectConfigurationProperties3.FileAlignment%2A>.  
  
## Vea también  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [Cómo: Modificar las propiedades y los valores de configuración del proyecto](http://msdn.microsoft.com/es-es/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)