---
title: "Cómo: llamar a una función de Windows que adopta tipos sin signo (Visual Basic) | Documentos de Microsoft"
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
- Windows functions, calling
- unsigned data types
- UShort data type, using
- functions [Visual Basic], calling Windows functions
- ULong data type, using
- UInteger data type, using
- data types [Visual Basic], using
- unsigned types
- data types [Visual Basic], unsigned
- data types [Visual Basic], numeric
- unsigned types, using
ms.assetid: c2c0e712-8dc2-43b9-b4c6-345fbb02e7ce
caps.latest.revision: 18
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
ms.openlocfilehash: fbff07f4923b0633a2bc9b4fd558d9d51f64370a
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-call-a-windows-function-that-takes-unsigned-types-visual-basic"></a>Cómo: Llamar a una función de Windows que adopta tipos sin signo (Visual Basic)
Si está utilizando una clase, módulo o estructura que tiene miembros de tipos enteros sin signo, puede tener acceso a estos miembros con [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].  
  
### <a name="to-call-a-windows-function-that-takes-an-unsigned-type"></a>Llamar a una función de Windows que toma un tipo sin signo  
  
1.  Use un [instrucción Declare](../../../visual-basic/language-reference/statements/declare-statement.md) saber [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] qué biblioteca contiene la función, qué nombre tiene en esa biblioteca, ¿cuál es su secuencia de llamada y cómo convertir las cadenas al llamarla.  
  
2.  En el `Declare` instrucción, utilice `UInteger`, `ULong`, `UShort`, o `Byte` según corresponda para cada parámetro con un tipo sin signo.  
  
3.  Consulte la documentación de la función de Windows que esté llamando para buscar los nombres y valores de las constantes que utiliza. Muchos de ellos se definen en el archivo WinUser.h.  
  
4.  Declare las constantes necesarias en su código. Muchas constantes de Windows son valores sin signo de 32 bits, y deberá declarar estas `As``UInteger`.  
  
5.  Llame a la función de la manera normal. En el ejemplo siguiente se llama a la función de Windows `MessageBox`, que toma un argumento de entero sin signo.  
  
    ```  
    Public Class windowsMessage  
        Private Declare Auto Function mb Lib "user32.dll" Alias "MessageBox" (  
            ByVal hWnd As Integer,   
            ByVal lpText As String,   
            ByVal lpCaption As String,   
            ByVal uType As UInteger) As Integer  
        Private Const MB_OK As UInteger = 0  
        Private Const MB_ICONEXCLAMATION As UInteger = &H30  
        Private Const IDOK As UInteger = 1  
        Private Const IDCLOSE As UInteger = 8  
        Private Const c As UInteger = MB_OK Or MB_ICONEXCLAMATION  
        Public Function messageThroughWindows() As String  
            Dim r As Integer = mb(0, "Click OK if you see this!",   
                "Windows API call", c)  
            Dim s As String = "Windows API MessageBox returned " &  
                 CStr(r)& vbCrLf & "(IDOK = " & CStr(IDOK) &  
                 ", IDCLOSE = " & CStr(IDCLOSE) & ")"  
            Return s  
        End Function  
    End Class  
    ```  
  
     Puede probar la función `messageThroughWindows` con el código siguiente.  
  
    ```  
    Public Sub consumeWindowsMessage()  
        Dim w As New windowsMessage  
        w.messageThroughWindows()  
    End Sub  
    ```  
  
    > [!CAUTION]
    >  El `UInteger`, `ULong`, `UShort`, y `SByte` tipos de datos no son parte de la [independencia del lenguaje y componentes independientes del lenguaje](https://msdn.microsoft.com/library/12a7a7h3) (CLS), por lo que el código conforme a CLS no puede utilizar un componente que los utiliza.  
  
    > [!IMPORTANT]
    >  Realizar una llamada a código no administrado, como la interfaz de programación de aplicaciones (API) de Windows expone su código a posibles riesgos de seguridad.  
  
    > [!IMPORTANT]
    >  Al llamar a la API de Windows requiere permiso de código no administrado, lo que podría afectar a su ejecución en situaciones de confianza parcial. Para obtener más información, consulte <xref:System.Security.Permissions.SecurityPermission>y [permisos de acceso de código](http://msdn.microsoft.com/en-us/e5ae402f-6dda-4732-bbe8-77296630f675).</xref:System.Security.Permissions.SecurityPermission>  
  
## <a name="see-also"></a>Vea también  
 [Tipos de datos](../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Tipo de datos entero](../../../visual-basic/language-reference/data-types/integer-data-type.md)   
 [Tipo de datos UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)   
 [Declare (instrucción)](../../../visual-basic/language-reference/statements/declare-statement.md)   
 [Tutorial: Llamar a las API de Windows](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)
