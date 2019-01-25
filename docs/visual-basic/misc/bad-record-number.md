---
title: Número de registro incorrecto
ms.date: 07/20/2015
f1_keywords:
- vbrID63
ms.assetid: 1fcc33f8-822a-4de9-a6e3-228ddb5824a6
ms.openlocfilehash: fbf1a2db97d0474fb758ff5ed572e94395a187da
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54664763"
---
# <a name="bad-record-number"></a>Número de registro incorrecto
El número de registro de la instrucción `a FileGet`, `FilePut`, `FileGetObject`o `FilePutObject` es menor o igual que cero.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Compruebe los cálculos usados para generar el número de registro. Compruebe la ortografía de las variables que contienen el número de registro o usadas para calcular números de registro. Un nombre de variable mal escrito se declara implícitamente y se inicializa en cero, a menos que use `Option Explicit On` en el módulo.  
  
## <a name="see-also"></a>Vea también
- [Option Explicit (instrucción)](../../visual-basic/language-reference/statements/option-explicit-statement.md)
