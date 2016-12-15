---
title: "Long (Tipo de datos, Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.Long"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "& (carácter de tipo identificador)"
  - "tipos de datos [Visual Basic], asignar"
  - "tipos de datos [Visual Basic], integrales"
  - "caracteres de tipo identificador, &"
  - "números enteros"
  - "enteros, tipos de datos"
  - "enteros, tipos"
  - "tipos de datos integrales"
  - "L (carácter de tipo literal)"
  - "caracteres de tipo literal, L"
  - "Long (tipo de datos)"
  - "Long (palabra clave)"
  - "números, enteros"
  - "números, enteros"
  - "números enteros"
ms.assetid: b4770c34-1804-4f8c-b512-c10b0893e516
caps.latest.revision: 20
caps.handback.revision: 20
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Long (Tipo de datos, Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Contiene enteros de 64 bits \(8 bytes\) con signo cuyo valor se sitúa entre \-9.223.372.036.854.775.808 y 9.223.372.036.854.775.807 \(9,2... E\+18\).  
  
## Comentarios  
 Utilice el tipo de datos `Long` para incluir números enteros demasiado grandes para ajustarse en el tipo de datos `Integer`.  
  
 El valor predeterminado de `Long` es 0.  
  
## Sugerencias de programación  
  
-   **Consideraciones de interoperabilidad.** Si interactúa con componentes que no se han escrito para .NET Framework, por ejemplo objetos de automatización o COM, recuerde que `Long` tiene un ancho de datos diferente \(32 bits\) en otros entornos.  Al pasar un argumento de 32 bits a esos componentes, declárelo en el código de Visual Basic como `Integer` en lugar de `Long`.  
  
     Además, la automatización no admite enteros de 64 bits en Windows 95, Windows 98, Windows ME o Windows 2000.  No puede pasar un argumento de Visual Basic `Long` a un componente de Automatización en estos sistemas operativos.  
  
-   **Ampliación.** El tipo de datos `Long` se amplía a `Decimal`, `Single` o `Double`.  Esto significa que  `Long` se puede convertir en cualquiera de estos tipos sin que se produzca un error <xref:System.OverflowException?displayProperty=fullName>.  
  
-   **Caracteres de tipo.** Al agregar el carácter de tipo literal `L` a un literal, el tipo de datos se convierte al tipo de datos `Long`.  Si se agrega el carácter de tipo identificador `&` a cualquier identificador, se convierte su tipo de datos al tipo `Long`.  
  
-   **Tipo en Framework.** El tipo correspondiente en .NET Framework es la estructura <xref:System.Int64?displayProperty=fullName>.  
  
## Vea también  
 <xref:System.Int64>   
 [Tipos de datos](../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Integer \(Tipo de datos\)](../../../visual-basic/language-reference/data-types/integer-data-type.md)   
 [Short \(Tipo de datos\)](../../../visual-basic/language-reference/data-types/short-data-type.md)   
 [Funciones de conversión de tipos](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [Resumen de conversión](../../../visual-basic/language-reference/keywords/conversion-summary.md)   
 [Uso eficiente de tipos de datos](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)