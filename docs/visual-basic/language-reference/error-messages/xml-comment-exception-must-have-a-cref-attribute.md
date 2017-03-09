---
title: "La excepci&#243;n del comentario XML debe tener un atributo &#39;cref&#39; | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc42319"
  - "vbc42319"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC42319"
ms.assetid: 62eeeba3-6811-48be-b1ef-c2e4feda3177
caps.latest.revision: 13
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 13
---
# La excepci&#243;n del comentario XML debe tener un atributo &#39;cref&#39;
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

La etiqueta \< exception \> proporciona una manera de documentar las excepciones que puede producir un método.  El atributo `cref` necesario designa el nombre de un miembro, que comprueba el generador de la documentación.  Si el miembro existe, se convierte al nombre de elemento canónico en el archivo de documentación.  
  
 **Identificador de error:** BC42319  
  
### Para corregir este error  
  
-   Agregue el atributo `cref` a la excepción como sigue:  
  
    ```  
    '''<exception cref="member">description</exception>  
    ```  
  
## Vea también  
 [\<exception\>](../../../visual-basic/language-reference/xmldoc/exception.md)   
 [Cómo: Crear documentación XML](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)   
 [Etiquetas XML para comentarios](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)