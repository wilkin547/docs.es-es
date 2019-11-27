---
title: 'Cómo: Llamar a un procedimiento que no devuelve un valor'
ms.date: 07/20/2015
helpviewer_keywords:
- procedure calls [Visual Basic], returning values
- Visual Basic code, procedures
- procedures [Visual Basic], calling
ms.assetid: 259b49a3-a3c1-4254-ba8c-73cdc4127703
ms.openlocfilehash: 3a5de98c6edf795a11bd9f0465aa6919f09eebfa
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74340959"
---
# <a name="how-to-call-a-procedure-that-does-not-return-a-value-visual-basic"></a>Cómo: Llamar a un procedimiento que no devuelve un valor (Visual Basic)
Un procedimiento `Sub` no devuelve un valor al código de llamada. Se llama explícitamente con una instrucción de llamada independiente. No se puede llamar simplemente mediante su nombre en una expresión.  
  
### <a name="to-call-a-sub-procedure"></a>Para llamar a un procedimiento Sub  
  
1. Especifique el nombre del procedimiento `Sub`.  
  
2. Siga el nombre del procedimiento entre paréntesis para incluir la lista de argumentos. Si no hay ningún argumento, puede omitir los paréntesis opcionalmente. Sin embargo, el uso de los paréntesis facilita la lectura del código.  
  
3. Coloque los argumentos en la lista de argumentos entre paréntesis, separados por comas. Asegúrese de proporcionar los argumentos en el mismo orden en el que el procedimiento `Sub` define los parámetros correspondientes.  
  
     En el ejemplo siguiente se llama a la función <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> Visual Basic para activar una ventana de la aplicación. <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> toma el título de la ventana como su único argumento. No devuelve un valor al código de llamada. Si no se está ejecutando un proceso del Bloc de notas, el ejemplo produce una <xref:System.ArgumentException>. En el procedimiento `Shell` se da por supuesto que las aplicaciones se encuentran en las rutas de acceso especificadas.  
  
     [!code-vb[VbVbalrCatRef#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCatRef/VB/Class1.vb#11)]  
  
## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.Interaction.Shell%2A>
- <xref:System.ArgumentException>
- [Procedimientos](./index.md)
- [Subprocedimientos](./sub-procedures.md)
- [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)
- [Sub (instrucción)](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [Crear un procedimiento](./how-to-create-a-procedure.md)
- [Llamar a un procedimiento que devuelve un valor](./how-to-call-a-procedure-that-returns-a-value.md)
- [Cómo: llamar a un controlador de eventos en Visual Basic](./how-to-call-an-event-handler.md)
