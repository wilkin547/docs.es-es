---
title: Error al cargar la biblioteca DLL (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID48
ms.assetid: 4226cd1f-028c-477d-88a5-cb57f7e0cdc8
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: cc557dcc6709178b6519adb56f31debcbd1d1c39
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="error-in-loading-dll-visual-basic"></a>Error al cargar la biblioteca DLL (Visual Basic)
Una biblioteca de vínculos dinámicos (DLL) es una biblioteca especificada en el `Lib` cláusula de una `Declare` instrucción. Posibles causas de este error son:  
  
-   El archivo no es ejecutable de DLL.  
  
-   El archivo no es una DLL de Microsoft Windows.  
  
-   La DLL hace referencia a otra DLL que no está presente.  
  
-   El archivo DLL o la DLL que se hace referencia no está en un directorio especificado en la ruta de acceso.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Si el archivo es un archivo de texto de origen y, por lo tanto, no DLL ejecutable, debe ser compilado y vinculado a una formato ejecutable de DLL.  
  
-   Si el archivo no es una DLL de Microsoft Windows, obtenga el equivalente de Microsoft Windows.  
  
-   Si el archivo DLL hace referencia a otra DLL que no está presente, obtenga el archivo DLL que se hace referencia y que esté disponible.  
  
-   Si el archivo DLL o la DLL que se hace referencia no está en un directorio especificado por la ruta de acceso, mueva la DLL en un directorio que se hace referencia.  
  
## <a name="see-also"></a>Vea también  
 [Declare (instrucción)](../../../visual-basic/language-reference/statements/declare-statement.md)
