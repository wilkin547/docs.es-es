---
title: WriteOnly (Visual Basic)
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
ms.openlocfilehash: b6c8a05a4575c5d1ec01aa1b2badf2129c54bc2a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54522783"
---
# <a name="writeonly-visual-basic"></a>WriteOnly (Visual Basic)
Especifica que se puede escribir pero no leer una propiedad.  
  
## <a name="remarks"></a>Comentarios  
  
## <a name="rules"></a>Reglas  
 **Contexto de declaración.** Solo se puede usar `WriteOnly` en un nivel de módulo. Esto significa que el contexto de declaración de un `WriteOnly` propiedad debe ser una clase, estructura o módulo y no puede ser un archivo de código fuente, el espacio de nombres o el procedimiento.  
  
 Puede declarar una propiedad como `WriteOnly`, pero no una variable.  
  
## <a name="when-to-use-writeonly"></a>Cuándo usar WriteOnly  
 A veces desea que el código usado para poder establecer un valor pero no descubrir lo que es. Por ejemplo, datos confidenciales, como un número de registro de redes sociales o una contraseña, deben protegerse contra el acceso por cualquier componente que no se ha establecido. En estos casos, puede usar un `WriteOnly` propiedad para establecer el valor.  
  
> [!IMPORTANT]
>  Al definir y usar un `WriteOnly` propiedad, considere la posibilidad de las medidas de protección adicionales siguientes:  
  
-   **Se ha invalidado.** Si la propiedad es un miembro de una clase, permite que de forma predeterminada [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)y no se ha declarado `Overridable` o `MustOverride`. Esto impide que una clase derivada lo que el acceso no deseado a través de una invalidación.  
  
-   **Nivel de acceso.** Si mantiene los datos confidenciales de la propiedad en una o más variables, declárelos [privada](../../../visual-basic/language-reference/modifiers/private.md) para que ningún otro código puede tener acceso a ellos.  
  
-   **Cifrado.** Store todos los datos confidenciales en un formato cifrado en lugar de en texto sin formato. Si algún modo, código malintencionado obtiene acceso a esa área de memoria, es más difícil de hacer uso de los datos. Cifrado también es útil si es necesario serializar los datos confidenciales.  
  
-   **Restablecer.** Cuando se termina la clase, estructura o módulo que define la propiedad, restablecer la información confidencial a los valores predeterminados o a otros valores sin sentido. Esto proporciona protección adicional cuando se libera esa área de memoria para el acceso general.  
  
-   **Persistencia.** No se conservan los datos confidenciales, por ejemplo en el disco, si se puede evitar. Además, no escribir los datos confidenciales en el Portapapeles.  
  
 El `WriteOnly` modificador se puede usar en este contexto:  
  
 [Property (instrucción)](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="see-also"></a>Vea también
- [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)
- [Private](../../../visual-basic/language-reference/modifiers/private.md)
- [Palabras clave](../../../visual-basic/language-reference/keywords/index.md)
