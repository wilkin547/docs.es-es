---
title: WriteOnly
ms.date: 07/20/2015
f1_keywords:
- WriteOnly
- vb.WriteOnly
helpviewer_keywords:
- write-only properties
- WriteOnly keyword [Visual Basic]
- sensitive data, protecting
- properties [Visual Basic], write-only
- sensitive data
ms.assetid: 488d2899-b09f-4cee-92f0-6f9f9fc4f944
ms.openlocfilehash: 847617ea6534089857a759fbea3bb16a3a5a36a1
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344192"
---
# <a name="writeonly-visual-basic"></a>WriteOnly (Visual Basic)
Especifica que una propiedad se puede escribir pero no leer.  
  
## <a name="remarks"></a>Comentarios  
  
## <a name="rules"></a>Reglas  
 **Contexto de declaración.** Solo se puede usar `WriteOnly` en un nivel de módulo. Esto significa que el contexto de la declaración de una propiedad `WriteOnly` debe ser una clase, una estructura o un módulo, y no puede ser un archivo de código fuente, un espacio de nombres o un procedimiento.  
  
 Puede declarar una propiedad como `WriteOnly`, pero no una variable.  
  
## <a name="when-to-use-writeonly"></a>Cuándo usar WriteOnly  
 A veces, desea que el código de consumo pueda establecer un valor, pero no detectar lo que es. Por ejemplo, los datos confidenciales, como un número de registro social o una contraseña, deben protegerse contra el acceso de cualquier componente que no lo haya configurado. En estos casos, puede usar una propiedad `WriteOnly` para establecer el valor.  
  
> [!IMPORTANT]
> Al definir y usar una propiedad `WriteOnly`, tenga en cuenta las siguientes medidas de protección adicionales:  
  
- **Invalidar.** Si la propiedad es un miembro de una clase, permita que el valor predeterminado sea [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)y no lo declare `Overridable` o `MustOverride`. Esto evita que una clase derivada realice un acceso no deseado a través de una invalidación.  
  
- **Nivel de acceso.** Si contiene los datos confidenciales de la propiedad en una o varias variables, declárelo [para que](../../../visual-basic/language-reference/modifiers/private.md) ningún otro código pueda acceder a ellos.  
  
- **Cifra.** Almacene todos los datos confidenciales en formato cifrado en lugar de en texto sin formato. Si el código malintencionado obtiene acceso de algún modo a esa área de memoria, es más difícil hacer uso de los datos. El cifrado también es útil si es necesario serializar la información confidencial.  
  
- **Restablecer.** Cuando se termine la clase, estructura o módulo que define la propiedad, restablezca los datos confidenciales a los valores predeterminados o a otros valores sin sentido. Esto proporciona protección adicional cuando se libera ese área de memoria para el acceso general.  
  
- **Persistence.** No conserve los datos confidenciales, por ejemplo, en el disco, si puede evitarlo. Además, no escriba datos confidenciales en el portapapeles.  
  
 El modificador `WriteOnly` se puede usar en este contexto:  
  
 [Property (instrucción)](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="see-also"></a>Vea también

- [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)
- [Private](../../../visual-basic/language-reference/modifiers/private.md)
- [Palabras clave](../../../visual-basic/language-reference/keywords/index.md)
