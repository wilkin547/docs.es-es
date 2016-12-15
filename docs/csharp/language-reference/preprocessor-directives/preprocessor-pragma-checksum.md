---
title: "#pragma checksum (Referencia del programador de C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "#pragma checksum"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "#pragma (suma de comprobación) [C#]"
ms.assetid: 3673e4ca-6098-4ec1-890f-8fceb2a794a2
caps.latest.revision: 11
caps.handback.revision: 11
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# #pragma checksum (Referencia del programador de C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Genera sumas de comprobación de los archivos de código fuente para ayudar en la depuración de páginas [!INCLUDE[vstecasp](../../../csharp/language-reference/preprocessor-directives/includes/vstecasp_md.md)].  
  
## Sintaxis  
  
```  
#pragma checksum "filename" "{guid}" "checksum bytes"  
```  
  
#### Parámetros  
 `"filename"`  
 Nombre del archivo al que hay que supervisar los cambios o actualizaciones.  
  
 `"{guid}"`  
 Identificador único global \(GUID\) del archivo.  
  
 `"checksum_bytes"`  
 La cadena de dígitos hexadecimales representa a los bytes de la suma de comprobación.  Esta cadena debe tener un número par de dígitos hexadecimales,  Un número de dígitos impar da lugar a una advertencia de error en tiempo de compilación y a la omisión de la directiva.  
  
## Comentarios  
 El depurador de Visual Studio utiliza una suma de comprobación para asegurarse de que siempre encuentra el código de fuente correcto.  El compilador calcula la suma de comprobación del archivo de código fuente y, a continuación, emite el resultado al archivo de base de datos de programa \(PDB\).  El depurador utiliza el archivo PDB para comparar la suma de comprobación calculada del archivo de código fuente.  
  
 Esta solución no funciona para proyectos de [!INCLUDE[vstecasp](../../../csharp/language-reference/preprocessor-directives/includes/vstecasp_md.md)], porque la suma de comprobación calculada es del archivo de código fuente generado, en vez del archivo .aspx.  Para solucionar este problema, `#pragma checksum` ofrece compatibilidad con la suma de comprobación para páginas [!INCLUDE[vstecasp](../../../csharp/language-reference/preprocessor-directives/includes/vstecasp_md.md)].  
  
 Al crear un proyecto [!INCLUDE[vstecasp](../../../csharp/language-reference/preprocessor-directives/includes/vstecasp_md.md)] en [!INCLUDE[csprcs](../../../csharp/includes/csprcs_md.md)], el archivo de código fuente generado contiene una suma de comprobación del archivo .aspx, a partir del cual se genera el código fuente.  Seguidamente, el compilador escribe esta información en el archivo PDB.  
  
 Si el compilador no encuentra ninguna directiva `#pragma checksum` en el archivo, calcula la suma de comprobación y escribe el valor en el archivo PDB.  
  
## Ejemplo  
  
```  
class TestClass  
{  
    static int Main()  
    {  
        #pragma checksum "file.cs" "{3673e4ca-6098-4ec1-890f-8fceb2a794a2}" "{012345678AB}" // New checksum  
    }  
}  
```  
  
## Vea también  
 [Referencia de C\#](../../../csharp/language-reference/index.md)   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Directivas de preprocesador de C\#](../../../csharp/language-reference/preprocessor-directives/index.md)