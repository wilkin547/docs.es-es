---
title: La excepción del comentario XML debe tener un atributo 'cref'
ms.date: 07/20/2015
f1_keywords:
- bc42319
- vbc42319
helpviewer_keywords:
- BC42319
ms.assetid: 62eeeba3-6811-48be-b1ef-c2e4feda3177
ms.openlocfilehash: 2e57dc63cb7ad8b2e061296a082d6fa79b464f08
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/28/2019
ms.locfileid: "71592040"
---
# <a name="xml-comment-exception-must-have-a-cref-attribute"></a>La excepción del comentario XML debe tener un atributo 'cref'
La etiqueta \<exception > proporciona una manera de documentar las excepciones que puede producir un método. El atributo `cref` necesario designa el nombre de un miembro, que se comprueba en el generador de documentación. Si el miembro existe, se traduce al nombre de elemento canónico en el archivo de documentación.  
  
 **IDENTIFICADOR de error:** BC42319  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
- Agregue el atributo `cref` a la excepción como se indica a continuación:  
  
    xml  
    <exception cref="member">Descripción</exception> de ' ' '  
    ```  
  
## See also

- [\<exception>](../../../visual-basic/language-reference/xmldoc/exception.md)
- [How to: Create XML Documentation](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
- [XML Comment Tags](../../../visual-basic/language-reference/xmldoc/index.md)
