---
title: Reanudar sin error
ms.date: 07/20/2015
f1_keywords:
- vbrID20
ms.assetid: f9631804-fd36-4443-b36c-30db827e6176
ms.openlocfilehash: b6b565c88acadca048ade22ab00ac68539725f78
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400375"
---
# <a name="resume-without-error"></a>Reanudar sin error
Una `Resume` instrucción aparecía fuera del código de control de errores o el código saltó a un controlador de errores, aunque no se haya producido ningún error.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1. Mueva la `Resume` instrucción a un controlador de errores o elimínela.  
  
2. Los saltos a las etiquetas no pueden producirse en los procedimientos, por lo que busque en el procedimiento la etiqueta que identifica el controlador de errores. Si encuentra una etiqueta duplicada especificada como destino de una `GoTo` instrucción que no es una `On Error GoTo` instrucción, cambie la etiqueta de línea para que coincida con su destino previsto.  
  
## <a name="see-also"></a>Consulte también

- [Resume (Instrucción)](../statements/resume-statement.md)
- [Instrucción On Error](../statements/on-error-statement.md)
