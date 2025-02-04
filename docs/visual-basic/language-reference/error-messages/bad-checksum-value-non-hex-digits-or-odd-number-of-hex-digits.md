---
description: 'Más información acerca de: BC42033: valor de suma de comprobación incorrecto, dígitos no hexadecimales o número impar de dígitos hexadecimales'
title: Valor de suma de comprobación incorrecto; no tiene dígitos hexadecimales o el número de dígitos hexadecimales es impar
ms.date: 07/20/2015
f1_keywords:
- bc42033
- vbc42033
helpviewer_keywords:
- BC42033
ms.assetid: 4575554d-3615-46e4-9c6a-18e9c338e4ed
ms.openlocfilehash: 051ee0e8ec8b87be4d5feeac8298c0e7a71baea7
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "102103886"
---
# <a name="bc42033-bad-checksum-value-non-hex-digits-or-odd-number-of-hex-digits"></a>BC42033: valor de suma de comprobación incorrecto, dígitos no hexadecimales o número impar de dígitos hexadecimales

Un valor de suma de comprobación contiene dígitos hexadecimales no válidos o un número impar de dígitos.

 Cuando ASP.NET genera un archivo de origen de Visual Basic (extensión .vb), calcula una suma de comprobación y la coloca en un archivo se origen oculto que se identifica por medio de `#externalchecksum`. Un usuario también puede generar un archivo .vb con el mismo fin, aunque lo más conveniente es dejar este proceso para uso interno.

 De forma predeterminada, este mensaje es una advertencia. Para obtener información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).

 **Identificador de error:** BC42033

## <a name="to-correct-this-error"></a>Para corregir este error

1. Si ASP.NET genera el archivo de origen de Visual Basic, reinicie la compilación del proyecto.

2. Si esta advertencia persiste tras el reinicio, reinstale ASP.NET e intente compilar de nuevo.

3. Si la advertencia persiste o no usa ASP.NET, reúna información sobre las circunstancias y notifíquelo a los Servicios de soporte técnico de Microsoft.

## <a name="see-also"></a>Consulte también

- [ASP.NET Overview](/aspnet/overview) (Información general de ASP.NET)
- [Opciones de comentarios de Visual Studio](/visualstudio/ide/feedback-options)
