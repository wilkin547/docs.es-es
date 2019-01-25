---
title: Error al cargar la biblioteca DLL (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vbrID48
ms.assetid: 4226cd1f-028c-477d-88a5-cb57f7e0cdc8
ms.openlocfilehash: 76a0a443fd9f8a6dec5ead24bc75c97d89d6c36b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54518467"
---
# <a name="error-in-loading-dll-visual-basic"></a>Error al cargar la biblioteca DLL (Visual Basic)
Una biblioteca de vínculos dinámicos (DLL) es una biblioteca especificada en el `Lib` cláusula de una `Declare` instrucción. Posibles causas de este error son:  
  
-   El archivo no es ejecutable de DLL.  
  
-   El archivo no es un archivo DLL de Windows de Microsoft.  
  
-   El archivo DLL hace referencia a otro archivo DLL que no está presente.  
  
-   El archivo DLL o un archivo DLL que se hace referencia no está en un directorio especificado en la ruta de acceso.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Si el archivo es un archivo de texto de origen y, por lo tanto, no DLL ejecutable, debe estar compilado y vinculado a una formato ejecutable de DLL.  
  
-   Si el archivo no es una DLL de Windows de Microsoft, obtenga el equivalente de Windows Microsoft.  
  
-   Si el archivo DLL hace referencia a otro archivo DLL que no está presente, obtenga el archivo DLL que se hace referencia y que esté disponible.  
  
-   Si el archivo DLL o un archivo DLL que se hace referencia no está en un directorio especificado por la ruta de acceso, mueva el archivo DLL en un directorio que se hace referencia.  
  
## <a name="see-also"></a>Vea también
- [Declare (instrucción)](../../../visual-basic/language-reference/statements/declare-statement.md)
