---
title: "\"<interfacename>.<membername>\" ya se ha implementado mediante la clase base \"<baseclassname>\". Se supone que <type> se implementa de nuevo"
ms.date: 07/20/2015
f1_keywords:
- vbc42015
- bc42015
helpviewer_keywords:
- BC42015
ms.assetid: 658c070a-113e-4bd8-b294-12c243191160
ms.openlocfilehash: 8137f6b1712b6a0752a991f5a3d598b5f958252c
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162822"
---
# <a name="bc42015-interfacenamemembername-is-already-implemented-by-the-base-class-baseclassname-re-implementation-of-type-assumed"></a>\<interfacename> \<membername> La clase base ' ' ya ha implementado BC42015: '. ' \<baseclassname> . Se supone que \<type> se implementa de nuevo

Una propiedad, un procedimiento o un evento en una clase derivada usa una `Implements` cláusula que especifica un miembro de interfaz que ya está implementado en la clase base.

 Una clase derivada puede volver a implementar un miembro de interfaz implementado por su clase base. Esto no es el mismo que reemplazar la implementación de la clase base. Para obtener más información, consulte [Implements](../statements/implements-clause.md).

 De forma predeterminada, este mensaje es una advertencia. Para obtener información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).

 **Identificador de error:** BC42015

## <a name="to-correct-this-error"></a>Para corregir este error

- Si piensa volver a implementar el miembro de interfaz, no es necesario realizar ninguna acción. El código de la clase derivada tiene acceso al miembro reimplementado a menos que use la `MyBase` palabra clave para tener acceso a la implementación de la clase base.

- Si no tiene pensado volver a implementar el miembro de interfaz, quite la cláusula `Implements` de la declaración de propiedad, procedimiento o evento.

## <a name="see-also"></a>Vea también

- [Interfaces](../../programming-guide/language-features/interfaces/index.md)
