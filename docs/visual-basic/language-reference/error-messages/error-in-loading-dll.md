---
title: Error al cargar DLL
ms.date: 07/20/2015
f1_keywords:
- vbrID48
ms.assetid: 4226cd1f-028c-477d-88a5-cb57f7e0cdc8
ms.openlocfilehash: 35733fe2e20d46207f6cfdaee32f6559fceed6eb
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874385"
---
# <a name="error-in-loading-dll-visual-basic"></a>Error al cargar la biblioteca DLL (Visual Basic)

Una biblioteca de vínculos dinámicos (DLL) es una biblioteca especificada en la `Lib` cláusula de una `Declare` instrucción. Entre las posibles causas de este error se incluyen:  
  
- El archivo no es un ejecutable DLL.  
  
- El archivo no es una DLL de Microsoft Windows.  
  
- El archivo DLL hace referencia a otro archivo DLL que no está presente.  
  
- El archivo dll o el archivo DLL al que se hace referencia no se encuentra en un directorio especificado en la ruta de acceso.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
- Si el archivo es un archivo de texto de origen y, por lo tanto, no es un ejecutable DLL, se debe compilar y vincular a un formulario ejecutable DLL.  
  
- Si el archivo no es una DLL de Microsoft Windows, obtenga el equivalente de Microsoft Windows.  
  
- Si el archivo DLL hace referencia a otro archivo DLL que no está presente, obtenga el archivo DLL al que se hace referencia y haga que esté disponible.  
  
- Si el archivo dll o el archivo DLL al que se hace referencia no se encuentra en un directorio especificado por la ruta de acceso, mueva el archivo DLL a un directorio al que se hace referencia.  
  
## <a name="see-also"></a>Consulte también

- [Declare Statement](../statements/declare-statement.md)
