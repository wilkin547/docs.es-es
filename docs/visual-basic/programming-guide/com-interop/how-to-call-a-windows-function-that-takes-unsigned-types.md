---
title: 'Cómo: Llamar a una función de Windows que adopta tipos sin signo (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- Windows functions [Visual Basic], calling
- unsigned data types [Visual Basic]
- UShort data type [Visual Basic], using
- functions [Visual Basic], calling Windows functions
- ULong data type [Visual Basic], using
- UInteger data type [Visual Basic], using
- data types [Visual Basic], using
- unsigned types [Visual Basic]
- data types [Visual Basic], unsigned
- data types [Visual Basic], numeric
- unsigned types [Visual Basic], using
ms.assetid: c2c0e712-8dc2-43b9-b4c6-345fbb02e7ce
ms.openlocfilehash: d66b74f06abe6b337c24859c444f7a8c2aa52c13
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43421528"
---
# <a name="how-to-call-a-windows-function-that-takes-unsigned-types-visual-basic"></a>Cómo: Llamar a una función de Windows que adopta tipos sin signo (Visual Basic)
Si está utilizando una clase, módulo o estructura que tiene miembros de tipos enteros sin signo, puede tener acceso a estos miembros con Visual Basic.  
  
### <a name="to-call-a-windows-function-that-takes-an-unsigned-type"></a>Para llamar a una función de Windows que toma un tipo sin signo  
  
1.  Use un [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) para indicar a Visual Basic de biblioteca que contiene la función, lo que es su nombre en esa biblioteca, ¿cuál es su secuencia de llamada y cómo convertir cadenas al llamarla.  
  
2.  En el `Declare` declaración, use `UInteger`, `ULong`, `UShort`, o `Byte` según corresponda para cada parámetro con un tipo sin signo.  
  
3.  Consulte la documentación de la función de Windows que esté llamando para buscar los nombres y valores de las constantes que utiliza. Muchas de ellas se definen en el archivo WinUser.h.  
  
4.  Declare las constantes necesarias en el código. Muchas de las constantes de Windows son valores sin signo de 32 bits, y se deben declarar estos `As``UInteger`.  
  
5.  Llame a la función de la manera normal. El ejemplo siguiente se llama a la función de Windows `MessageBox`, que toma un argumento de entero sin signo.  
  
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
    >  El `UInteger`, `ULong`, `UShort`, y `SByte` tipos de datos no son parte de la [independencia del lenguaje y componentes independientes del lenguaje](../../../standard/language-independence-and-language-independent-components.md) (CLS), por lo que el código conforme a CLS no puede utilizar un componente que los utiliza.  
  
    > [!IMPORTANT]
    >  Realizar una llamada a código no administrado, como la interfaz de programación de aplicaciones (API), Windows expone su código a posibles riesgos de seguridad.  
  
    > [!IMPORTANT]
    >  Llamar a la API de Windows requiere el permiso de código no administrado, lo que podría afectar a su ejecución en situaciones de confianza parcial. Para obtener más información, consulte <xref:System.Security.Permissions.SecurityPermission> y [permisos de acceso del código](https://msdn.microsoft.com/library/e5ae402f-6dda-4732-bbe8-77296630f675).  
  
## <a name="see-also"></a>Vea también  
 [Tipos de datos](../../../visual-basic/language-reference/data-types/index.md)  
 [Integer (tipo de datos)](../../../visual-basic/language-reference/data-types/integer-data-type.md)  
 [UInteger (tipo de datos)](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
 [Declare (instrucción)](../../../visual-basic/language-reference/statements/declare-statement.md)  
 [Tutorial: Llamar a las API de Windows](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)
