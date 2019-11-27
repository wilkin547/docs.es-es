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
ms.openlocfilehash: 668ffbc7b8db73a706c5771bb0734a77f8fc0206
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351244"
---
# <a name="error-statement"></a>Error (Instrucción)
Simula la aparición de un error.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
Error errornumber  
```  
  
## <a name="parts"></a>Elementos  
 `errornumber`  
 Obligatorio. Puede ser cualquier número de error válido.  
  
## <a name="remarks"></a>Comentarios  
 La instrucción `Error` se admite por compatibilidad con versiones anteriores. En el nuevo código, especialmente al crear objetos, utilice el método `Raise` del objeto `Err` para generar errores en tiempo de ejecución.  
  
 Si se define `errornumber`, la instrucción `Error` llama al controlador de errores después de que se asignen los siguientes valores predeterminados a las propiedades del objeto `Err`:  
  
|Propiedad|Valor|  
|--------------|-----------|  
|`Number`|Valor especificado como argumento para `Error` instrucción. Puede ser cualquier número de error válido.|  
|`Source`|Nombre del proyecto de Visual Basic actual.|  
|`Description`|Expresión de cadena que corresponde al valor devuelto de la función `Error` para el `Number`especificado, si esta cadena existe. Si la cadena no existe, `Description` contiene una cadena de longitud cero ("").|  
|`HelpFile`|La unidad, ruta de acceso y nombre de archivo completos del archivo de ayuda Visual Basic adecuado.|  
|`HelpContext`|El identificador de contexto del archivo de ayuda Visual Basic adecuado para el error correspondiente a la propiedad `Number`.|  
|`LastDLLError`|Nulo.|  
  
 Si no existe ningún controlador de errores, o si no se habilita ninguno, se crea un mensaje de error que se muestra en las propiedades del objeto `Err`.  
  
> [!NOTE]
> Algunas aplicaciones host de Visual Basic no pueden crear objetos. Consulte la documentación de la aplicación host para determinar si puede crear clases y objetos.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se utiliza la instrucción `Error` para generar el número de error 11.  
  
```vb  
On Error Resume Next   ' Defer error handling.  
Error 11   ' Simulate the "Division by zero" error.  
```  
  
## <a name="requirements"></a>Requisitos  
 **Espacio de nombres:** [Microsoft. VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)  
  
 **Ensamblado:** Biblioteca en tiempo de ejecución de Visual Basic (en Microsoft. VisualBasic. dll)  
  
## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.ErrObject.Clear%2A>
- <xref:Microsoft.VisualBasic.Information.Err%2A>
- <xref:Microsoft.VisualBasic.ErrObject.Raise%2A>
- [On Error (instrucción)](../../../visual-basic/language-reference/statements/on-error-statement.md)
- [Resume (instrucción)](../../../visual-basic/language-reference/statements/resume-statement.md)
- [Mensajes de error](../../../visual-basic/language-reference/error-messages/index.md)
