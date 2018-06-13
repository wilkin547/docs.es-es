---
title: Error (Instrucción)
ms.date: 07/20/2015
f1_keywords:
- vb.error
helpviewer_keywords:
- Error statement [Visual Basic], syntax
- Error statement [Visual Basic]
- Error keyword [Visual Basic]
- run-time errors [Visual Basic], codes
- errors [Visual Basic], simulating
ms.assetid: 85cd5c59-5224-4f02-aaf5-fcfefab17a29
ms.openlocfilehash: 3ecfe18392de15dc937d90565b49641415dd7e0a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33603891"
---
# <a name="error-statement"></a>Error (Instrucción)
Simula la aparición de un error.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
Error errornumber  
```  
  
## <a name="parts"></a>Elementos  
 `errornumber`  
 Requerido. Puede ser cualquier número de error válido.  
  
## <a name="remarks"></a>Comentarios  
 El `Error` instrucción se admite por compatibilidad con versiones anteriores. En el nuevo código, especialmente al crear objetos, utilice la `Err` del objeto `Raise` método para generar errores en tiempo de ejecución.  
  
 Si `errornumber` se define, el `Error` instrucción llama al controlador de errores después de las propiedades de la `Err` objeto se asignan los valores predeterminados siguientes:  
  
|Property|Valor|  
|--------------|-----------|  
|`Number`|El valor especificado como argumento para `Error` instrucción. Puede ser cualquier número de error válido.|  
|`Source`|Nombre del proyecto actual de Visual Basic.|  
|`Description`|Corresponde al valor devuelto de una expresión de cadena del `Error` función para el elemento especificado `Number`, si esta cadena no existe. Si la cadena no existe, `Description` contiene una cadena de longitud cero ("").|  
|`HelpFile`|El nombre completo con unidad, ruta de acceso y nombre de archivo del archivo de Ayuda de Visual Basic apropiado.|  
|`HelpContext`|La Ayuda de Visual Basic correspondiente archivo de Id. de contexto para el error correspondiente a la `Number` propiedad.|  
|`LastDLLError`|Es cero.|  
  
 Si no hay ningún controlador de error existe, o si ninguno está habilitado, se crea un mensaje de error y se muestra en la `Err` propiedades del objeto.  
  
> [!NOTE]
>  Algunas aplicaciones de host de Visual Basic no pueden crear objetos. Consulte la documentación de la aplicación host para determinar si puede crear clases y objetos.  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo se utiliza la `Error` instrucción que se va a generar el error número 11.  
  
```  
On Error Resume Next   ' Defer error handling.  
Error 11   ' Simulate the "Division by zero" error.  
```  
  
## <a name="requirements"></a>Requisitos  
 **Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)  
  
 **Ensamblado:** biblioteca de tiempo de ejecución de Visual Basic (en Microsoft.VisualBasic.dll)  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualBasic.ErrObject.Clear%2A>  
 <xref:Microsoft.VisualBasic.Information.Err%2A>  
 <xref:Microsoft.VisualBasic.ErrObject.Raise%2A>  
 [On Error (instrucción)](../../../visual-basic/language-reference/statements/on-error-statement.md)  
 [Resume (instrucción)](../../../visual-basic/language-reference/statements/resume-statement.md)  
 [Mensajes de error](../../../visual-basic/language-reference/error-messages/index.md)
