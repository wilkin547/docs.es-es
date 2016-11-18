---
title: 'Ejemplo de expresiones regulares: buscar etiquetas HREF'
description: 'Ejemplo de expresiones regulares: buscar etiquetas HREF'
keywords: .NET, .NET Core
author: stevehoag
manager: wpickett
ms.date: 07/28/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: d6484880-bdac-47cd-b5e5-9419c9ed14cd
translationtype: Human Translation
ms.sourcegitcommit: fb00da6505c9edb6a49d2003ae9bcb8e74c11d6c
ms.openlocfilehash: 494ceeb2cc3bbf77098d2b6145690e7229ed3b9f

---

# <a name="regular-expression-example-scanning-for-hrefs"></a>Ejemplo de expresiones regulares: buscar etiquetas HREF

En el ejemplo siguiente se busca una cadena de entrada y se muestran todos los valores href="…" y sus ubicaciones en la cadena. 

## <a name="the-regex-object"></a>El objeto Regex

Dado que el método `DumpHRefs` puede llamarse varias veces desde el código de usuario, usa el método `static` [Regex.Match(String, String, RegexOptions)](xref:System.Text.RegularExpressions.Regex.Match(System.String,System.String,System.Text.RegularExpressions.RegexOptions)). Esto permite que el motor de expresiones regulares almacene en caché la expresión regular y evita la sobrecarga que se produciría al crear instancias de un nuevo objeto [Regex](xref:System.Text.RegularExpressions.Regex) cada vez que se llamara al método. Después, se usa un objeto [Match](xref:System.Text.RegularExpressions.Match) para iterar todas las coincidencias de la cadena. 

```csharp
private static void DumpHRefs(string inputString) 
{
   Match m;
   string HRefPattern = "href\\s*=\\s*(?:[\"'](?<1>[^\"']*)[\"']|(?<1>\\S+))";

   try {
      m = Regex.Match(inputString, HRefPattern, 
                      RegexOptions.IgnoreCase | RegexOptions.Compiled, 
                      TimeSpan.FromSeconds(1));
      while (m.Success)
      {
         Console.WriteLine("Found href " + m.Groups[1] + " at " 
            + m.Groups[1].Index);
         m = m.NextMatch();
      }   
   }
   catch (RegexMatchTimeoutException) {
      Console.WriteLine("The matching operation timed out.");
   }
}
```

```vb
Private Sub DumpHRefs(inputString As String) 
   Dim m As Match
   Dim HRefPattern As String = "href\s*=\s*(?:[""'](?<1>[^""']*)[""']|(?<1>\S+))"

   Try
      m = Regex.Match(inputString, HRefPattern, _ 
                      RegexOptions.IgnoreCase Or RegexOptions.Compiled,
                      TimeSpan.FromSeconds(1))
      Do While m.Success
         Console.WriteLine("Found href {0} at {1}.", _
                           m.Groups(1), m.Groups(1).Index)
         m = m.NextMatch()
      Loop   
   Catch e As RegexMatchTimeoutException
      Console.WriteLine("The matching operation timed out.")
   End Try
End Sub
```

En el ejemplo siguiente se muestra la llamada al método `DumpHRefs`.

```csharp
public static void Main()
{
   string inputString = "My favorite web sites include:</P>" +
                        "<A HREF=\"http://msdn2.microsoft.com\">" +
                        "MSDN Home Page</A></P>" +
                        "<A HREF=\"http://www.microsoft.com\">" +
                        "Microsoft Corporation Home Page</A></P>" +
                        "<A HREF=\"http://blogs.msdn.com/bclteam\">" +
                        ".NET Base Class Library blog</A></P>";
   DumpHRefs(inputString);                     

}
// The example displays the following output:
//       Found href http://msdn2.microsoft.com at 43
//       Found href http://www.microsoft.com at 102
//       Found href http://blogs.msdn.com/bclteam at 176
```

```vb
Public Sub Main()
   Dim inputString As String = "My favorite web sites include:</P>" & _
                               "<A HREF=""http://msdn2.microsoft.com"">" & _
                               "MSDN Home Page</A></P>" & _
                               "<A HREF=""http://www.microsoft.com"">" & _
                               "Microsoft Corporation Home Page</A></P>" & _
                               "<A HREF=""http://blogs.msdn.com/bclteam"">" & _
                               ".NET Base Class Library blog</A></P>"
   DumpHRefs(inputString)                     
End Sub
' The example displays the following output:
'       Found href http://msdn2.microsoft.com at 43
'       Found href http://www.microsoft.com at 102
'       Found href http://blogs.msdn.com/bclteam/) at 176
```

El patrón de la expresión regular `href\s*=\s*(?:["']&#40;?<1>[^"']*)["']|(?<1>\S+))` se interpreta como se muestra en la tabla siguiente.

Modelo | Descripción
------- | ----------- 
`href` | Coincide con la cadena literal "href". La búsqueda no distingue entre mayúsculas y minúsculas.
`\s*` | Busca coincidencias con cero o más caracteres de espacio en blanco.
`=` |`Coincide con el signo igual.
`\s*` | Busca coincidencias con cero o más caracteres de espacio en blanco.
`(?:["']&#40;?<1>[^"']*)"&#124;(?<1>\S+))` | Coincide con uno de los siguientes sin asignar el resultado a un grupo capturado: una comilla o un apóstrofo, seguido de cero o más apariciones de cualquier carácter que no sea una comilla o un apóstrofo, seguido por una comilla o un apóstrofo. El grupo con nombre `1` se incluye en este patrón. -o- Uno o varios caracteres que no son espacio en blanco. El grupo con nombre `1` se incluye en este patrón.
`(?<1>[^"']*)` | Asigna cero o más apariciones de cualquier carácter que no sea apóstrofo o comilla al grupo de captura con nombre `1`.
`"(?<1>\S+)` | Asigna uno o varios caracteres que no sean un espacio en blanco al grupo de captura con nombre `1`.
 
## <a name="match-result-class"></a>Clase de resultado Match

Los resultados de la búsqueda se almacenan en la clase [Match](xref:System.Text.RegularExpressions.Match), que proporciona acceso a todas las subcadenas extraídas por la búsqueda. También recuerda la cadena buscada y la expresión regular que se usa, por lo que puede llamar al método [Match.NextMatch](xref:System.Text.RegularExpressions.Match.NextMatch) para realizar otra búsqueda desde donde terminó la anterior.

## <a name="explicitly-named-captures"></a>Capturas con nombre explícito

En las expresiones regulares tradicionales, los paréntesis de captura se numeran secuencialmente de forma automática. Esto origina dos problemas. En primer lugar, si se modifica una expresión regular al insertar o quitar un conjunto de paréntesis, se debe reescribir todo el código que hace referencia a las capturas numeradas para reflejar la nueva numeración. En segundo lugar, puesto que a menudo se usan diferentes conjuntos de paréntesis para proporcionar expresiones alternativas para una coincidencia aceptable, puede resultar difícil determinar cuál de las dos expresiones devolvió realmente un resultado.

Para abordar estos problemas, la clase [Regex](xref:System.Text.RegularExpressions.Regex) admite la sintaxis `(?<name>…)` para capturar una coincidencia en una ranura especificada (el nombre dado a la ranura puede ser una cadena o un entero; los enteros se pueden recuperar con más rapidez). Así, las coincidencias alternativas para la misma cadena se pueden dirigir todas al mismo lugar. En caso de conflicto, la última coincidencia situada en la ranura es la coincidencia correcta. (Pero está disponible una lista completa de varias coincidencias para una única ranura. Consulte la colección [Group.Captures](xref:System.Text.RegularExpressions.Group.Captures) para obtener más información.)

## <a name="see-also"></a>Vea también

[Expresiones regulares de .NET](regular-expressions.md)

[Ejemplos de expresiones regulares](regex-examples.md)




<!--HONumber=Nov16_HO3-->


