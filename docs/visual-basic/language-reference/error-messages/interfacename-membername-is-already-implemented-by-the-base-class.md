---
title: "La clase base &#39;&lt;nombre de clase base&gt;&#39; ha implementado ya &#39;&lt;nombre de interfaz&gt;.&lt;nombre de miembro&gt;&#39;. Se supone que &lt;tipo&gt; se implementa de nuevo | Microsoft Docs"
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
  - "vbc42015"
  - "bc42015"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC42015"
ms.assetid: 658c070a-113e-4bd8-b294-12c243191160
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# La clase base &#39;&lt;nombre de clase base&gt;&#39; ha implementado ya &#39;&lt;nombre de interfaz&gt;.&lt;nombre de miembro&gt;&#39;. Se supone que &lt;tipo&gt; se implementa de nuevo
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Una propiedad, procedimiento o evento de una clase derivada utiliza una cláusula `Implements` que especifica un miembro de interfaz que ya está implementado en la clase base.  
  
 Una clase derivada puede volver a implementar un miembro de interfaz que es implementado por su clase base.  Esto no equivale a reemplazar la implementación de la clase base.  Para obtener más información, vea [Implements](../../../visual-basic/language-reference/statements/implements-clause.md).  
  
 De forma predeterminada, este mensaje es una advertencia.  Para obtener más información sobre cómo ocultar las advertencias o tratarlas como errores, vea [Configurar advertencias en Visual Basic](/visual-studio/ide/configuring-warnings-in-visual-basic).  
  
 **Identificador de error:** BC42015  
  
### Para corregir este error  
  
-   Si tiene intención de volver a implementar el miembro de interfaz, no es necesario realizar ninguna acción.  El código de la clase derivada tiene acceso al miembro nuevamente implementado, excepto si utiliza la palabra clave `MyBase` para tener acceso a la implementación de la clase base.  
  
-   Si no piensa volver a implementar el miembro de interfaz, quite la cláusula `Implements` de la propiedad, procedimiento o declaración de evento.  
  
## Vea también  
 [Interfaces](../../../visual-basic/programming-guide/language-features/interfaces/index.md)