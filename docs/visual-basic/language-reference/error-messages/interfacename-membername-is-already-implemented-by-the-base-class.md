---
title: "'<interfacename>. <membername>'ya está implementado por la clase base'<baseclassname>'. Reimplementación de <type> supone"
ms.date: 07/20/2015
f1_keywords:
- vbc42015
- bc42015
helpviewer_keywords:
- BC42015
ms.assetid: 658c070a-113e-4bd8-b294-12c243191160
ms.openlocfilehash: 5943eff5fa7e68da9905e3e589eea264c06943c1
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64593316"
---
# <a name="interfacenamemembername-is-already-implemented-by-the-base-class-baseclassname-re-implementation-of-type-assumed"></a>'\<nombreDeInterfaz >. \<membername >' ya está implementado por la clase base\<nombredeclasebase >'. Reimplementación de \<tipo > supone
Una propiedad, procedimiento o evento en una clase derivada utiliza una `Implements` cláusula que especifica un miembro de interfaz que ya está implementado en la clase base.  
  
 Una clase derivada puede volver a implementar un miembro de interfaz implementado por su clase base. Esto no es el mismo que reemplazar la implementación de la clase base. Para obtener más información, consulte [Implements](../../../visual-basic/language-reference/statements/implements-clause.md).  
  
 De forma predeterminada, este mensaje es una advertencia. Para obtener más información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Identificador de error:** BC42015  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
- Si piensa volver a implementar el miembro de interfaz, no es necesario realizar ninguna acción. Código de la clase derivada tiene acceso al miembro nuevamente implementado a menos que use el `MyBase` palabra clave para acceder a la implementación de la clase base.  
  
- Si no tiene pensado volver a implementar el miembro de interfaz, quite la cláusula `Implements` de la declaración de propiedad, procedimiento o evento.  
  
## <a name="see-also"></a>Vea también

- [Interfaces](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
