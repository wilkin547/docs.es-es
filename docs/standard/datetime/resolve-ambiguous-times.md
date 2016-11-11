---
title: "Cómo resolver horas ambiguas"
description: "Cómo resolver horas ambiguas"
keywords: .NET, .NET Core
author: stevehoag
manager: wpickett
ms.date: 08/16/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: e86050c6-d16d-405e-8bba-7205945c9a81
translationtype: Human Translation
ms.sourcegitcommit: c40c28da09e8a122b542463c197196c82c81dd19
ms.openlocfilehash: e4e62607fd1bd3b4cee3e23a5863e1ba9e25ab03

---

# <a name="how-to-resolve-ambiguous-times"></a>Cómo resolver horas ambiguas

Una hora ambigua es aquella que se asigna a más de una hora universal coordinada (UTC). Esto sucede cuando la hora del reloj se atrasa, como durante la transición del horario de verano de una zona horaria al horario estándar. Cuando se enfrente a una hora ambigua, puede realizar una de las siguientes acciones:

* Piense cómo se corresponde esa hora con la hora UTC. Por ejemplo, puede dar por supuesto que una hora ambigua siempre se expresa en la hora estándar de la zona horaria.

* Si la hora ambigua es un dato introducido por el usuario, puede dejar que el usuario resuelva la ambigüedad.

Este artículo muestra cómo resolver una hora ambigua dando por supuesto que representa la hora estándar de la zona horaria.

## <a name="to-map-an-ambiguous-time-to-a-time-zones-standard-time"></a>Para asignar una hora ambigua a la hora estándar de una zona horaria

1. Llame al método [System.TimeZoneInfo.IsAmbiguousTime(DateTime)](xref:System.TimeZoneInfo.IsAmbiguousTime(System.DateTime)) o [System.TimeZoneInfo.IsAmbiguousTime(DateTimeOffset)](xref:System.TimeZoneInfo.IsAmbiguousTime(System.DateTimeOffset)) para determinar si la hora es ambigua.

2. Si la hora es ambigua, reste la hora al objeto [TimeSpan](xref:System.TimeSpan) devuelto por la propiedad [BaseUtcOffset](xref:System.TimeZoneInfo.BaseUtcOffset) de la zona horaria.

3. Llame al método [SpecifyKind](xref:System.DateTime.SpecifyKind(System.DateTime,System.DateTimeKind)) `static` (`Shared` en Visual Basic) para establecer la propiedad [Kind](xref:System.DateTime.Kind) del valor de fecha y hora UTC en [DateTimeKind.Utc](xref:System.DateTimeKind.Utc).

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra cómo convertir un valor [DateTime](xref:System.DateTime) ambiguo a UTC dando por supuesto que representa la hora estándar de la zona horaria local. 

```csharp
private DateTime ResolveAmbiguousTime(DateTime ambiguousTime)
{
   // Time is not ambiguous
   if (! TimeZoneInfo.Local.IsAmbiguousTime(ambiguousTime))
   { 
      return ambiguousTime; 
   }
   // Time is ambiguous
   else
   {
      DateTime utcTime = DateTime.SpecifyKind(ambiguousTime - TimeZoneInfo.Local.BaseUtcOffset, 
                                              DateTimeKind.Utc);      
      Console.WriteLine("{0} local time corresponds to {1} {2}.", 
                        ambiguousTime, utcTime, utcTime.Kind.ToString());
      return utcTime;            
   }   
}
```

```vb
Private Function ResolveAmbiguousTime(ambiguousTime As Date) As Date
   ' Time is not ambiguous
   If Not TimeZoneInfo.Local.IsAmbiguousTime(ambiguousTime) Then 
      Return TimeZoneInfo.ConvertTimeToUtc(ambiguousTime) 
   ' Time is ambiguous
   Else
      Dim utcTime As Date = DateTime.SpecifyKind(ambiguousTime - TimeZoneInfo.Local.BaseUtcOffset, DateTimeKind.Utc)      
      Console.WriteLine("{0} local time corresponds to {1} {2}.", ambiguousTime, utcTime, utcTime.Kind.ToString())
      Return utcTime            
   End If   
End Function
```

El ejemplo consta de un método denominado `ResolveAmbiguousTime` que determina si el valor [DateTime](xref:System.DateTime) pasado es ambiguo. Si el valor es ambiguo, el método devuelve un valor [DateTime](xref:System.DateTime) que representa la hora UTC correspondiente. El método trata esta conversión restando a la hora local el valor de la propiedad [BaseUtcOffset](xref:System.TimeZoneInfo.BaseUtcOffset) de la zona horaria local. 

Normalmente, una hora ambigua se controla mediante una llamada al método [GetAmbiguousTimeOffsets](xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets(System.DateTime)) para recuperar una matriz de objetos [TimeSpan](xref:System.TimeSpan) que contienen los desplazamientos posibles de la hora ambigua desde la hora UTC. Pero en este ejemplo se supone arbitrariamente que una hora ambigua siempre debe estar asignada a la hora estándar de la zona horaria. La propiedad [BaseUtcOffset](xref:System.TimeZoneInfo.BaseUtcOffset) devuelve la diferencia entre la hora UTC y la hora estándar de una zona horaria.

## <a name="see-also"></a>Vea también

[Fechas, horas y zonas horarias](index.md)

[Cómo: Permitir que los usuarios resuelvan horas ambiguas](let-users-resolve-ambiguous-times.md)




<!--HONumber=Nov16_HO1-->


