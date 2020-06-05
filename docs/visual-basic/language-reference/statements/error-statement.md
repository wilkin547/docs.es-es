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
ms.openlocfilehash: 35ba1f19654d1d23ac1ec73564bc36b0af4f6777
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404750"
---
# <a name="error-statement"></a>Error (Instrucción)
Simula la aparición de un error.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
Error errornumber  
```  
  
## <a name="parts"></a>Partes  
 `errornumber`  
 Necesario. Puede ser cualquier número de error válido.  
  
## <a name="remarks"></a>Observaciones  
 La `Error` instrucción se admite por compatibilidad con versiones anteriores. En el nuevo código, especialmente al crear objetos, utilice el `Err` método del objeto `Raise` para generar errores en tiempo de ejecución.  
  
 Si `errornumber` se define, la `Error` instrucción llama al controlador de errores después de que `Err` se asignen los siguientes valores predeterminados a las propiedades del objeto:  
  
|Propiedad|Valor|  
|--------------|-----------|  
|`Number`|Valor especificado como argumento para la `Error` instrucción. Puede ser cualquier número de error válido.|  
|`Source`|Nombre del proyecto de Visual Basic actual.|  
|`Description`|Expresión de cadena que corresponde al valor devuelto de la `Error` función para el especificado `Number` , si esta cadena existe. Si la cadena no existe, `Description` contiene una cadena de longitud cero ("").|  
|`HelpFile`|La unidad, ruta de acceso y nombre de archivo completos del archivo de ayuda Visual Basic adecuado.|  
|`HelpContext`|El identificador de contexto del archivo de ayuda Visual Basic adecuado para el error correspondiente a la `Number` propiedad.|  
|`LastDLLError`|Cero.|  
  
 Si no existe ningún controlador de errores, o si no se habilita ninguno, se crea un mensaje de error y se muestra en las `Err` propiedades del objeto.  
  
> [!NOTE]
> Algunas aplicaciones host de Visual Basic no pueden crear objetos. Consulte la documentación de la aplicación host para determinar si puede crear clases y objetos.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se utiliza la `Error` instrucción para generar el número de error 11.  
  
```vb  
On Error Resume Next   ' Defer error handling.  
Error 11   ' Simulate the "Division by zero" error.  
```  
  
## <a name="requirements"></a>Requisitos  
 **Espacio de nombres:** [Microsoft. VisualBasic](../runtime-library-members.md)  
  
 **Ensamblado:** Biblioteca en tiempo de ejecución de Visual Basic (en Microsoft. VisualBasic. dll)  
  
## <a name="see-also"></a>Consulte también

- <xref:Microsoft.VisualBasic.ErrObject.Clear%2A>
- <xref:Microsoft.VisualBasic.Information.Err%2A>
- <xref:Microsoft.VisualBasic.ErrObject.Raise%2A>
- [Instrucción On Error](on-error-statement.md)
- [Resume (Instrucción)](resume-statement.md)
- [Mensajes de error](../error-messages/index.md)
