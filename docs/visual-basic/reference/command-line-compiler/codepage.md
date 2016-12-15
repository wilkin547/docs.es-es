---
title: "/codepage (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "/codepage (opción del compilador) [Visual Basic]"
  - "codepage (opción del compilador) [Visual Basic]"
  - "-codepage (opción del compilador) [Visual Basic]"
ms.assetid: be36ec33-6800-4505-838c-4124564f5cc9
caps.latest.revision: 17
caps.handback.revision: 17
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# /codepage (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Especifica la página de códigos que debe utilizarse para todos los archivos de código fuente en la compilación.  
  
## Sintaxis  
  
```  
/codepage:id  
```  
  
## Argumentos  
  
|||  
|-|-|  
|Término|Definición|  
|`id`|Requerido.  El compilador utiliza la página de códigos especificada por `id` para interpretar la codificación de los archivos de código fuente.|  
  
## Comentarios  
 Para compilar el código fuente guardado con una codificación concreta, puede utilizar `/codepage` para especificar la página de códigos que debería utilizarse.  La opción `/codepage` se aplica a todos los archivos de código fuente de la compilación.  Para obtener más información, vea [Codificación de caracteres en .NET Framework](../Topic/Character%20Encoding%20in%20the%20.NET%20Framework.md).  
  
 La opción `/codepage` no es necesaria si los archivos de código fuente se guardaron utilizando la página de códigos ANSI actual, Unicode o UTF\-8 con una firma.  [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] guarda de forma predeterminada todos los archivos de código fuente con la página de códigos ANSI actual, a menos que el usuario especifique otra codificación en el cuadro de diálogo **Codificación**.  [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] utiliza el cuadro de diálogo **Codificación** para abrir archivos de código fuente guardados con una página de códigos diferente.  
  
> [!NOTE]
>  La opción `/codepage` no está disponible en el entorno de desarrollo de [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)]; solo está disponible cuando se compila desde la línea de comandos.  
  
## Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)