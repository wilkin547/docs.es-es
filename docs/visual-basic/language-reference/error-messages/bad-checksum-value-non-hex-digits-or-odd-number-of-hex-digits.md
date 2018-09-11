---
title: Valor de suma de comprobación incorrecto; no tiene dígitos hexadecimales o el número de dígitos hexadecimales es impar
ms.date: 07/20/2015
f1_keywords:
- bc42033
- vbc42033
helpviewer_keywords:
- BC42033
ms.assetid: 4575554d-3615-46e4-9c6a-18e9c338e4ed
ms.openlocfilehash: e682c2c23dd6fe80aee87d2a86b3df2dae66b802
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2018
ms.locfileid: "44276466"
---
# <a name="bad-checksum-value-non-hex-digits-or-odd-number-of-hex-digits"></a>Valor de suma de comprobación incorrecto; no tiene dígitos hexadecimales o el número de dígitos hexadecimales es impar
Un valor de suma de comprobación contiene dígitos hexadecimales no válidos o un número impar de dígitos.  
  
 Cuando ASP.NET genera un archivo de origen de Visual Basic (extensión .vb), calcula una suma de comprobación y la coloca en un archivo se origen oculto que se identifica por medio de `#externalchecksum`. Un usuario también puede generar un archivo .vb con el mismo fin, aunque lo más conveniente es dejar este proceso para uso interno.  
  
 De forma predeterminada, este mensaje es una advertencia. Para obtener información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Identificador de error:** BC42033  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Si ASP.NET genera el archivo de origen de Visual Basic, reinicie la compilación del proyecto.  
  
2.  Si esta advertencia persiste tras el reinicio, reinstale ASP.NET e intente compilar de nuevo.  
  
3.  Si la advertencia persiste o no usa ASP.NET, reúna información sobre las circunstancias y notifíquelo a los Servicios de soporte técnico de Microsoft.  
  
## <a name="see-also"></a>Vea también

- [ASP.NET Overview](/aspnet/overview) (Información general de ASP.NET)  
- [Hable con nosotros](/visualstudio/ide/talk-to-us)
