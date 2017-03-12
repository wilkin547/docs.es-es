---
redirect_url: /dotnet/articles/csharp/programming-guide/interop/
caps.handback.revision: 31
---
# Interoperabilidad (Gu&#237;a de programaci&#243;n de C#)
La interoperabilidad permite conservar y aprovechar las inversiones existentes en código no administrado.  El código que se ejecuta bajo el control de Common Language Runtime \(CLR\) se denomina *código administrado*, mientras que el código que se ejecuta fuera de CLR se denomina *código no administrado*.  Los componentes COM, COM\+, C\+\+, los componentes de ActiveX y la API de Microsoft Win32 son ejemplos de código no administrado.  
  
 La aplicación [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] habilita la interoperabilidad con el código no administrado a través de los servicios de invocación de plataforma, el espacio de nombres <xref:System.Runtime.InteropServices> y la interoperabilidad C\+\+ y COM.  
  
## En esta sección  
 [Información general sobre interoperabilidad](../../../csharp/programming-guide/interop/interoperability-overview.md)  
 Describe métodos de interoperabilidad entre código administrado y no administrado de C\#.  
  
 [Cómo: Tener acceso a objetos de interoperabilidad de Office mediante las características de Visual C\#](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md)  
 Describe las características que se incluyen en Visual C\# 2010 para facilitar la programación de Office.  
  
 [Cómo: Utilizar propiedades indizadas en la programación de interoperabilidad COM](../../../csharp/programming-guide/interop/how-to-use-indexed-properties-in-com-interop-rogramming.md)  
 Describe cómo usar las propiedades indizadas para tener acceso a las propiedades COM que tienen los parámetros.  
  
 [Cómo: Utilizar la invocación de plataforma para reproducir un archivo de sonido](../../../csharp/programming-guide/interop/how-to-use-platform-invoke-to-play-a-wave-file.md)  
 Describe cómo utilizar los servicios de invocación de plataforma para reproducir un archivo de sonido .wav en el sistema operativo Windows.  
  
 [Tutorial: Programación de Office](../../../csharp/programming-guide/interop/walkthrough-office-programming.md)  
 Muestra cómo crear un libro de Excel y un documento de Word que contiene un vínculo al libro.  
  
 [Clase COM de ejemplo](../../../csharp/programming-guide/interop/example-com-class.md)  
 Muestra cómo exponer una clase de C\# como objeto COM.  
  
## Especificación del lenguaje C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Vea también  
 <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A?displayProperty=fullName>   
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Interoperating with Unmanaged Code](../Topic/Interoperating%20with%20Unmanaged%20Code.md)   
 [Tutorial: Programación de Office](../../../csharp/programming-guide/interop/walkthrough-office-programming.md)