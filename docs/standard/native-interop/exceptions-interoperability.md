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
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794619"
---
# <a name="working-with-interop-exceptions-in-unmanaged-code"></a>Trabajar con excepciones de interoperabilidad en código no administrado

La interoperabilidad de excepciones de código no administrado solo se admite en plataformas Windows. Los problemas de portabilidad surgen en plataformas que no son de Windows. Dado que la ABI de UNIX no tiene ninguna definición para el control de excepciones, el código administrado no puede saber cómo funcionan los mecanismos de excepción en segundo plano. Por lo tanto, las excepciones pueden acabar dando lugar a comportamientos imprevisibles y bloqueos.

## <a name="setjmplongjmp-behaviors"></a>Comportamientos de setjmp/longjmp

No se admite la interoperabilidad con funciones de `setjmp` y `longjmp` C. No puede usar `longjmp` para omitir los marcos administrados.

Para obtener más información, consulte la [documentación de longjmp](https://docs.microsoft.com/cpp/c-runtime-library/reference/longjmp).

## <a name="see-also"></a>Vea también

- [Excepciones](index.md)
- [Interoperabilidad con bibliotecas nativas](https://www.mono-project.com/docs/advanced/pinvoke/#runtime-exception-propagation)
