---
title: Procedimiento apara llamar a un procedimiento que no devuelve un valor
ms.date: 07/20/2015
helpviewer_keywords:
- procedure calls [Visual Basic], returning values
- Visual Basic code, procedures
- procedures [Visual Basic], calling
ms.assetid: 259b49a3-a3c1-4254-ba8c-73cdc4127703
ms.openlocfilehash: 514d6e576b9b782387840ae04dcefa00de876aa9
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84388743"
---
# <a name="how-to-call-a-procedure-that-does-not-return-a-value-visual-basic"></a>Cómo: Llamar a un procedimiento que no devuelve un valor (Visual Basic)
Un `Sub` procedimiento no devuelve un valor al código de llamada. Se llama explícitamente con una instrucción de llamada independiente. No se puede llamar simplemente mediante su nombre en una expresión.  
  
### <a name="to-call-a-sub-procedure"></a>Para llamar a un procedimiento Sub  
  
1. Especifique el nombre del `Sub` procedimiento.  
  
2. Siga el nombre del procedimiento entre paréntesis para incluir la lista de argumentos. Si no hay ningún argumento, puede omitir los paréntesis opcionalmente. Sin embargo, el uso de los paréntesis facilita la lectura del código.  
  
3. Coloque los argumentos en la lista de argumentos entre paréntesis, separados por comas. Asegúrese de proporcionar los argumentos en el mismo orden en que el `Sub` procedimiento define los parámetros correspondientes.  
  
     En el ejemplo siguiente se llama <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> a la función Visual Basic para activar una ventana de la aplicación. <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A>toma el título de la ventana como su único argumento. No devuelve un valor al código de llamada. Si no se está ejecutando un proceso del Bloc de notas, el ejemplo produce una excepción <xref:System.ArgumentException> . `Shell`En el procedimiento se supone que las aplicaciones están en las rutas de acceso especificadas.  
  
     [!code-vb[VbVbalrCatRef#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCatRef/VB/Class1.vb#11)]  
  
## <a name="see-also"></a>Consulte también

- <xref:Microsoft.VisualBasic.Interaction.Shell%2A>
- <xref:System.ArgumentException>
- [Procedimientos](./index.md)
- [Procedimientos Sub](./sub-procedures.md)
- [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)
- [Instrucción Sub](../../../language-reference/statements/sub-statement.md)
- [Procedimiento para crear un procedimiento](./how-to-create-a-procedure.md)
- [Procedimiento para llamar a un procedimiento que devuelve un valor](./how-to-call-a-procedure-that-returns-a-value.md)
- [Cómo: Llamar a un controlador de eventos en Visual Basic](./how-to-call-an-event-handler.md)
