---
title: "C&#243;mo: Llamar a una funci&#243;n de Windows que adopta tipos sin signo (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "tipos de datos [Visual Basic], numéricos"
  - "tipos de datos [Visual Basic], sin signo"
  - "tipos de datos [Visual Basic], utilizar"
  - "funciones [Visual Basic], llamar a funciones de Windows"
  - "UInteger (tipo de datos), utilizar"
  - "ULong (tipo de datos), utilizar"
  - "tipos de datos sin signo"
  - "tipos sin signo"
  - "tipos sin signo, utilizar"
  - "UShort (tipo de datos), utilizar"
  - "funciones de Windows, llamar"
ms.assetid: c2c0e712-8dc2-43b9-b4c6-345fbb02e7ce
caps.latest.revision: 18
caps.handback.revision: 18
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# C&#243;mo: Llamar a una funci&#243;n de Windows que adopta tipos sin signo (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Si está utilizando una clase, módulo o estructura que tiene miembros de tipos de enteros sin signo, puede tener acceso a estos miembros con [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].  
  
### Para llamar a una función Windows que adopta un tipo sin signo  
  
1.  Utilice [Declare \(Instrucción\)](../../../visual-basic/language-reference/statements/declare-statement.md) para indicar a [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] qué biblioteca contiene la función, qué nombre tiene en esa biblioteca, cuál es su secuencia de llamada y cómo convertir las cadenas al llamarla.  
  
2.  En la instrucción `Declare`, utilice `UInteger`, `ULong`, `UShort` o `Byte` como corresponda a cada parámetro con un tipo sin signo.  
  
3.  Consulte la documentación de la función de Windows a la que está llamando para buscar los nombres y valores de las constantes que utiliza.  Muchos de éstas están definidas en el archivo WinUser.h.  
  
4.  Declare las constantes necesarias en su código.  Muchas constantes de Windows son valores sin signo de 32 bits y debe declararlas `As` `UInteger`.  
  
5.  Llame a la función de la manera normal.  En el ejemplo siguiente se llama a la función de Windows `MessageBox` que adopta un argumento de entero sin signo.  
  
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
    >  Los tipos de datos `UInteger`, `ULong`, `UShort` y `SByte` no forman parte de [Independencia del lenguaje y componentes independientes del lenguaje](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md) \(CLS\), por lo que el código conforme a CLS no puede utilizar un componente que los utiliza.  
  
    > [!IMPORTANT]
    >  Si realiza una llamada a un código no administrado, como la interfaz de programación de aplicaciones \(API\) de Windows, expone su código a un posible riesgo de seguridad.  
  
    > [!IMPORTANT]
    >  Para llamar a la API de Windows, se requiere un permiso de código no administrado que puede afectar a su ejecución en situaciones de confianza parcial.  Para obtener más información, vea <xref:System.Security.Permissions.SecurityPermission> y [Code Access Permissions](http://msdn.microsoft.com/es-es/e5ae402f-6dda-4732-bbe8-77296630f675).  
  
## Vea también  
 [Tipos de datos](../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Integer \(Tipo de datos\)](../../../visual-basic/language-reference/data-types/integer-data-type.md)   
 [UInteger \(Tipo de datos\)](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)   
 [Declare \(Instrucción\)](../../../visual-basic/language-reference/statements/declare-statement.md)   
 [Tutorial: Llamar a las API de Windows](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)