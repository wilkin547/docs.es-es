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
ms.openlocfilehash: 4f34f7f4ada3f8d61c9d855eab1b8b073a3d5ed8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="writeonly-visual-basic"></a>WriteOnly (Visual Basic)
Especifica que se puede escribir pero no leer una propiedad.  
  
## <a name="remarks"></a>Comentarios  
  
## <a name="rules"></a>Reglas  
 **Contexto de la declaración.** Solo se puede usar `WriteOnly` en un nivel de módulo. Esto significa que el contexto de la declaración de un `WriteOnly` propiedad debe ser una clase, estructura o módulo y no puede ser un archivo de código fuente, un espacio de nombres o un procedimiento.  
  
 Puede declarar una propiedad como `WriteOnly`, pero no una variable.  
  
## <a name="when-to-use-writeonly"></a>Cuándo se utiliza WriteOnly  
 A veces desea que el código usado para poder establecer un valor pero no descubrir lo que es. Por ejemplo, los datos confidenciales, como un número de registro social o una contraseña, deben protegerse contra el acceso por cualquier componente que no haya establecido. En estos casos, puede usar un `WriteOnly` propiedad para establecer el valor.  
  
> [!IMPORTANT]
>  Al definir y utilizar un `WriteOnly` propiedad, considere la posibilidad de las medidas de protección adicionales siguientes:  
  
-   **Reemplazar.** Si la propiedad es un miembro de una clase, permite que de forma predeterminada [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)y no se ha declarado `Overridable` o `MustOverride`. Esto impide que una clase derivada que realiza el acceso no deseado a través de una invalidación.  
  
-   **Nivel de acceso.** Si mantiene los datos confidenciales de la propiedad en una o más variables, declárelos [privada](../../../visual-basic/language-reference/modifiers/private.md) para que ningún otro código pueda acceder a ellos.  
  
-   **Cifrado.** Almacene todos los datos confidenciales en un formato cifrado en lugar de en texto sin formato. Si algún modo, el código malintencionado obtiene acceso a dicha área de memoria, es más difícil de tomar el uso de los datos. Cifrado también es útil si es necesario serializar los datos confidenciales.  
  
-   **Restablecer.** Cuando se termina la clase, estructura o módulo que define la propiedad, restablezca los datos sensibles a los valores predeterminados o a otros valores sin sentido. Esto proporciona una protección adicional cuando esa área de memoria se libera para el acceso general.  
  
-   **Persistencia.** No se conservan los datos confidenciales, por ejemplo en el disco, si se pueden evitar. Además, no escriba los datos confidenciales en el Portapapeles.  
  
 El `WriteOnly` modificador se puede usar en este contexto:  
  
 [Property (instrucción)](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="see-also"></a>Vea también  
 [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)  
 [Private](../../../visual-basic/language-reference/modifiers/private.md)  
 [Palabras clave](../../../visual-basic/language-reference/keywords/index.md)
