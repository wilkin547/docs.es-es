---
title: Interoperabilidad de excepciones
ms.date: 01/16/2020
ms.technology: dotnet-standard
helpviewer_keywords:
- unmanaged code, exceptions
- exceptions, unmanaged code
- interop, exceptions
- exceptions, interop
ms.openlocfilehash: 2aff71e97e1be0dbb584f4fe43c322cea86d2480
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794619"
---
# <a name="working-with-interop-exceptions-in-unmanaged-code"></a>Trabajo con excepciones de interoperabilidad en código no administrado

La interoperabilidad de excepciones de código no administrado solo se admite en plataformas Windows. En las plataformas que no son Windows surgen problemas de portabilidad. Dado que ABI de UNIX no tiene ninguna definición para el control de excepciones, el código administrado no puede saber cómo funcionan las entrañas de los mecanismos de excepción y, por lo tanto, las excepciones pueden acabar dando lugar a comportamientos imprevisibles y bloqueos.

## <a name="setjmplongjmp-behaviors"></a>Comportamientos de setjmp/longjmp

La interoperabilidad con funciones de C `setjmp` y `longjmp` no es posible. No se puede usar `longjmp` para omitir los marcos administrados.

Para más información, vea la [documentación de longjmp](https://docs.microsoft.com/cpp/c-runtime-library/reference/longjmp).

## <a name="see-also"></a>Vea también

- [Excepciones](index.md)
- [Interoperabilidad con bibliotecas nativas](https://www.mono-project.com/docs/advanced/pinvoke/#runtime-exception-propagation)
