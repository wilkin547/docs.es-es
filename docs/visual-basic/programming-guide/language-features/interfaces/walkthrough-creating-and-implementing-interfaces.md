---
title: Crear e implementar Interfaces (Visual Basic) | Documentos de Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- interfaces, walkthroughs
- interfaces, testing
- interface implementation, walkthrough
- interfaces, creating
ms.assetid: ded82af2-9f52-4232-98ef-fe458180f112
caps.latest.revision: 22
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 076bc8d33e97286c31f27a2016e39a25e9cec22c
ms.lasthandoff: 03/13/2017

---
# <a name="walkthrough-creating-and-implementing-interfaces-visual-basic"></a>Tutorial: Crear e implementar interfaces (Visual Basic)
Las interfaces describen las características de propiedades, métodos y eventos, pero dejan los detalles de implementación para las estructuras o clases.  
  
 Este tutorial muestra cómo declarar e implementar una interfaz.  
  
> [!NOTE]
>  Este tutorial no proporciona información sobre cómo crear una interfaz de usuario.  
  
[!INCLUDE[note_settings_general](../../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
### <a name="to-define-an-interface"></a>Para definir una interfaz  
  
1.  Abra un nuevo [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] el proyecto de aplicación de Windows.  
  
2.  Agregue un módulo nuevo al proyecto haciendo clic en **Agregar módulo** en el **proyecto** menú.  
  
3.  Nombre del nuevo módulo `Module1.vb` y haga clic en **agregar**. Se muestra el código del módulo nuevo.  
  
4.  Defina una interfaz denominada `TestInterface` en `Module1` escribiendo `Interface TestInterface` entre el `Module` y `End Module` instrucciones y, a continuación, presione ENTRAR. El **Editor de código** sangrías la `Interface` (palabra clave) y agrega un `End Interface` instrucción para formar un bloque de código.  
  
5.  Definir una propiedad, un método y un evento para la interfaz colocando el siguiente código entre el `Interface` y `End Interface` instrucciones:  
  
     [!code-vb[VbVbalrOOP&#98;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_1.vb)]  
  
## <a name="implementation"></a>Implementación  
 Observará que la sintaxis utilizada para declarar a los miembros de interfaz es diferente de la sintaxis utilizada para declarar a miembros de clase. Esta diferencia refleja el hecho de que las interfaces no pueden contener código de implementación.  
  
#### <a name="to-implement-the-interface"></a>Para implementar la interfaz  
  
1.  Agregue una clase denominada `ImplementationClass` agregando la siguiente instrucción para `Module1`, después la `End Interface` instrucción pero antes del `End Module` instrucción y, a continuación, presione ENTRAR:  
  
     [!code-vb[VbVbalrOOP&#99;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_2.vb)]  
  
     Si está trabajando dentro del entorno de desarrollo integrado, el **Editor de código** suministra una coincidencia `End Class` instrucción cuando presione ENTRAR.  
  
2.  Agregue el siguiente `Implements` instrucción `ImplementationClass`, que nombra la interfaz de la clase implementa:  
  
     [!code-vb[VbVbalrOOP Nº&100;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_3.vb)]  
  
     Cuando se muestra separada de otros elementos en la parte superior de una clase o estructura, el `Implements` instrucción indica que la clase o estructura implementa una interfaz.  
  
     Si está trabajando dentro del entorno de desarrollo integrado, el **Editor de código** implementa los miembros de clase requeridos por `TestInterface` cuando presione ENTRAR y puede omitir el paso siguiente.  
  
3.  Si no está trabajando dentro del entorno de desarrollo integrado, debe implementar todos los miembros de la interfaz `MyInterface`. Agregue el código siguiente a `ImplementationClass` implementar `Event1`, `Method1`, y `Prop1`:  
  
     [!code-vb[VbVbalrOOP&#101;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_4.vb)]  
  
     El `Implements` instrucción nombres de la interfaz y el miembro de interfaz implementado.  
  
4.  Completar la definición de `Prop1` agregando un campo privado a la clase que almacena el valor de propiedad:  
  
     [!code-vb[VbVbalrOOP&#102;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_5.vb)]  
  
     Devolver el valor de la `pval` de la propiedad de descriptor de acceso get.  
  
     [!code-vb[VbVbalrOOP&#103;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_6.vb)]  
  
     Establezca el valor de `pval` en la propiedad de descriptor de acceso set.  
  
     [!code-vb[VbVbalrOOP&#104;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_7.vb)]  
  
5.  Completar la definición de `Method1` agregando el código siguiente.  
  
     [!code-vb[VbVbalrOOP&#105;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_8.vb)]  
  
#### <a name="to-test-the-implementation-of-the-interface"></a>Para probar la implementación de la interfaz  
  
1.  Haga clic en el formulario de inicio para el proyecto en el **el Explorador de soluciones**y haga clic en **ver código**. El editor muestra la clase de formulario de inicio. De manera predeterminada, el formulario de inicio se denomina `Form1`.  
  
2.  Agregue el siguiente `testInstance` en la `Form1` clase:  
  
     [!code-vb[VbVbalrOOP&#120;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_9.vb)]  
  
     Mediante la declaración de `testInstance` como `WithEvents`, la `Form1` clase puede controlar sus eventos.  
  
3.  Agregue el siguiente controlador de eventos para el `Form1` clase para controlar los eventos generados por `testInstance`:  
  
     [!code-vb[VbVbalrOOP&#106;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_10.vb)]  
  
4.  Agregue una subrutina denominada `Test` a la `Form1` clase para probar la clase de implementación:  
  
     [!code-vb[VbVbalrOOP&#107;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_11.vb)]  
  
     El `Test` procedimiento crea una instancia de la clase que implementa `MyInterface`, asigna esa instancia a la `testInstance` campo, Establece una propiedad y ejecuta un método a través de la interfaz.  
  
5.  Agregue código para llamar a la `Test` procedimiento desde el `Form1 Load` procedimiento del formulario de inicio:  
  
     [!code-vb[VbVbalrOOP&#108;](../../../../visual-basic/misc/codesnippet/VisualBasic/walkthrough-creating-and-implementing-interfaces_12.vb)]  
  
6.  Ejecute el `Test` procedimiento presionando F5. Se muestra el mensaje "Prop1 se ha definido como 9". Se muestra después de hacer clic en Aceptar, el mensaje "el parámetro X de Method1 es 5". Haga clic en Aceptar y se muestra el mensaje "el controlador de eventos ha interceptado el evento".  
  
## <a name="see-also"></a>Vea también  
 [Implements (instrucción)](../../../../visual-basic/language-reference/statements/implements-statement.md)   
 [Interfaces](../../../../visual-basic/programming-guide/language-features/interfaces/index.md)   
 [Interface (instrucción)](../../../../visual-basic/language-reference/statements/interface-statement.md)   
 [Event (instrucción)](../../../../visual-basic/language-reference/statements/event-statement.md)

