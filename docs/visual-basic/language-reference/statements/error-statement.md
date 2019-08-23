---
title: Instrucción error (Visual Basic)
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
ms.openlocfilehash: 7b926214d3be7f5f57783a8599acf1bb1042f956
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69944454"
---
# <a name="error-statement"></a>Error (Instrucción)
Simula la aparición de un error.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
Error errornumber  
```  
  
## <a name="parts"></a>Elementos  
 `errornumber`  
 Necesario. Puede ser cualquier número de error válido.  
  
## <a name="remarks"></a>Comentarios  
 La `Error` instrucción se admite por compatibilidad con versiones anteriores. En el nuevo código, especialmente al crear objetos, utilice `Err` el método `Raise` del objeto para generar errores en tiempo de ejecución.  
  
 Si `errornumber` se define, la `Error` instrucción llama al controlador de errores `Err` después de que se asignen los siguientes valores predeterminados a las propiedades del objeto:  
  
|Propiedad|Value|  
|--------------|-----------|  
|`Number`|Valor especificado como argumento para `Error` la instrucción. Puede ser cualquier número de error válido.|  
|`Source`|Nombre del proyecto de Visual Basic actual.|  
|`Description`|Expresión de cadena que corresponde al valor devuelto `Error` de la función para `Number`el especificado, si esta cadena existe. Si la cadena no existe, `Description` contiene una cadena de longitud cero ("").|  
|`HelpFile`|La unidad, ruta de acceso y nombre de archivo completos del archivo de ayuda Visual Basic adecuado.|  
|`HelpContext`|El identificador de contexto del archivo de ayuda Visual Basic adecuado para el error `Number` correspondiente a la propiedad.|  
|`LastDLLError`|Nulo.|  
  
 Si no existe ningún controlador de errores, o si no se habilita ninguno, se crea un mensaje de error `Err` y se muestra en las propiedades del objeto.  
  
> [!NOTE]
> Algunas aplicaciones host de Visual Basic no pueden crear objetos. Consulte la documentación de la aplicación host para determinar si puede crear clases y objetos.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se `Error` utiliza la instrucción para generar el número de error 11.  
  
```  
On Error Resume Next   ' Defer error handling.  
Error 11   ' Simulate the "Division by zero" error.  
```  
  
## <a name="requirements"></a>Requisitos  
 **Espacio de nombres**: [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)  
  
 **Assembl** Biblioteca en tiempo de ejecución de Visual Basic (en Microsoft.VisualBasic.dll)  
  
## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.ErrObject.Clear%2A>
- <xref:Microsoft.VisualBasic.Information.Err%2A>
- <xref:Microsoft.VisualBasic.ErrObject.Raise%2A>
- [On Error (instrucción)](../../../visual-basic/language-reference/statements/on-error-statement.md)
- [Resume (instrucción)](../../../visual-basic/language-reference/statements/resume-statement.md)
- [Mensajes de error](../../../visual-basic/language-reference/error-messages/index.md)
