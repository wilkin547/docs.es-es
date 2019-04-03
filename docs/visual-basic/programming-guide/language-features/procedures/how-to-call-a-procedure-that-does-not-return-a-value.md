---
title: Filtrar Llamar a un procedimiento que no devuelve un valor (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- procedure calls [Visual Basic], returning values
- Visual Basic code, procedures
- procedures [Visual Basic], calling
ms.assetid: 259b49a3-a3c1-4254-ba8c-73cdc4127703
ms.openlocfilehash: 05b4b1cb29abff97c44c33d462375fc4d5ab159d
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58818584"
---
# <a name="how-to-call-a-procedure-that-does-not-return-a-value-visual-basic"></a>Filtrar Llamar a un procedimiento que no devuelve un valor (Visual Basic)
Un `Sub` procedimiento no devuelve un valor al código de llamada. Llama de forma explícita con una instrucción independiente que realiza la llamada. No se puede llamar a simplemente utilizando su nombre dentro de una expresión.  
  
### <a name="to-call-a-sub-procedure"></a>Para llamar a un procedimiento Sub  
  
1.  Especifique el nombre de la `Sub` procedimiento.  
  
2.  Siga el nombre del procedimiento con paréntesis para delimitar la lista de argumentos. Si no hay ningún argumento, opcionalmente, puede omitir los paréntesis. Sin embargo, el uso de los paréntesis hace que el código más fácil de leer.  
  
3.  Coloque los argumentos en la lista de argumentos entre paréntesis, separados por comas. Asegúrese de proporcionar los argumentos en el mismo orden que el `Sub` procedimiento define los parámetros correspondientes.  
  
     El ejemplo siguiente se llama a la de Visual Basic <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> función para activar una ventana de aplicación. <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> toma el título de ventana como único argumento. No se devuelve un valor al código de llamada. Si no se está ejecutando un proceso de Bloc de notas, en el ejemplo se produce un <xref:System.ArgumentException>. El `Shell` procedimiento se da por supuesto que las aplicaciones están en las rutas de acceso especificadas.  
  
     [!code-vb[VbVbalrCatRef#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCatRef/VB/Class1.vb#11)]  
  
## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.Interaction.Shell%2A>
- <xref:System.ArgumentException>
- [Procedimientos](./index.md)
- [Subprocedimientos](./sub-procedures.md)
- [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)
- [Sub (instrucción)](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [Cómo: Crear un procedimiento](./how-to-create-a-procedure.md)
- [Cómo: Llamar a un procedimiento que devuelve un valor](./how-to-call-a-procedure-that-returns-a-value.md)
- [Cómo: Llamar a un controlador de eventos en Visual Basic](./how-to-call-an-event-handler.md)
