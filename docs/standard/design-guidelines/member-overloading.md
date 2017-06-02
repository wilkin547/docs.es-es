---
title: "Sobrecarga de miembro | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "argumentos predeterminados"
  - "miembros sobrecargados [.NET Framework]"
  - "instrucciones de diseño de miembros [.NET Framework], sobrecarga"
  - "miembros sobrecargados"
  - "firmas de miembros"
ms.assetid: 964ba19e-8b94-4b5b-b1e3-5a0b531a0bb1
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# Sobrecarga de miembro
Sobrecarga de miembro significa crear dos o más miembros en el mismo tipo que solo difieren en el número o tipo de parámetros, pero tienen el mismo nombre. Por ejemplo, a continuación, el `WriteLine` se sobrecarga el método:  
  
```  
public static class Console {  
    public void WriteLine();  
    public void WriteLine(string value);  
    public void WriteLine(bool value);  
    ...  
}  
  
```  
  
 Dado que solo los métodos, constructores y propiedades indizadas pueden tener parámetros, se pueden sobrecargar sólo esos miembros.  
  
 La sobrecarga es una de las técnicas más importantes para mejorar la facilidad de uso, la productividad y mejorar la legibilidad de bibliotecas reutilizables. Sobrecarga en el número de parámetros permite proporcionar versiones más sencillas de constructores y métodos. Sobrecarga en el tipo de parámetro permite utilizar el mismo nombre de miembro para realizar operaciones idénticas en un conjunto seleccionado de diferentes tipos de miembros.  
  
 **✓ hacer** intenta utilizar nombres de parámetros descriptivos para indicar el valor predeterminado utilizado por las sobrecargas más cortas.  
  
 **Evitar X** variar arbitrariamente los nombres de parámetro en las sobrecargas. Si un parámetro de una sobrecarga representa la misma entrada como un parámetro de otra sobrecarga, los parámetros deben tener el mismo nombre.  
  
 **Evitar X** incoherente en el orden de los parámetros de sobrecarga miembros. Parámetros con el mismo nombre deberían aparecer en la misma posición en todas las sobrecargas.  
  
 **✓ hacer** hacer sólo la sobrecarga más larga sea virtual \(si se requiere la extensibilidad\). Simplemente deben llamar las sobrecargas más cortas mediante a una sobrecarga mayor.  
  
 **X no** use `ref` o `out` modificadores para sobrecargar miembros.  
  
 Algunos lenguajes no pueden resolver llamadas a sobrecargas así. Además, estas sobrecargas normalmente tienen una semántica completamente diferente y no deben ser sobrecargas pero dos métodos independientes en su lugar.  
  
 **X no** tienen sobrecargas con parámetros en la misma posición y tipos similares, pero con una semántica diferente.  
  
 **✓ hacer**  permitir `null` pasar argumentos opcionales.  
  
 **✓ hacer** utilizar miembros sobrecarga en lugar de definir miembros con argumentos predeterminados.  
  
 Los argumentos predeterminados no son compatibles con CLS.  
  
 *Partes © 2009, 2005 Microsoft Corporation. Todos los derechos reservados.*  
  
 *Reimpreso con permiso de Pearson Education, Inc. de [las directrices de diseño de Framework: convenciones, expresiones idiomáticas y patrones para las bibliotecas .NET de reutilizable, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison\-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*  
  
## Vea también  
 [Instrucciones de diseño de miembros](../../../docs/standard/design-guidelines/member.md)   
 [Instrucciones de diseño de Framework](../../../docs/standard/design-guidelines/index.md)