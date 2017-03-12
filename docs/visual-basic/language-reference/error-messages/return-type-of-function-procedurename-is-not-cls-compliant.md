---
title: "El tipo de valor devuelto de la funci&#243;n &#39;&lt;nombre de procedimiento&gt;&#39; no es compatible con CLS | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc40027"
  - "vbc40027"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC40027"
ms.assetid: 33c088c7-48e7-400c-920e-6d8967e1f3fc
caps.latest.revision: 13
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 13
---
# El tipo de valor devuelto de la funci&#243;n &#39;&lt;nombre de procedimiento&gt;&#39; no es compatible con CLS
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Un procedimiento de `Function` está marcado como `<CLSCompliant(True)>` pero devuelve un tipo marcado como `<CLSCompliant(False)>`, no está marcado, o no cumple los requisitos porque no es de un tipo compatible.  
  
 Para que un procedimiento sea compatible con la [Independencia del lenguaje y componentes independientes del lenguaje](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md) \(CLS\), debe utilizar sólo tipos conformes a CLS.  Esto se aplica a los tipos de los parámetros, el tipo de valor devuelto y los tipos de todas sus variables locales.  
  
 Los siguientes tipos de datos de [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] no son conformes a CLS:  
  
-   [SByte \(Tipo de datos\)](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
-   [UInteger \(Tipo de datos\)](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
-   [ULong \(Tipo de datos\)](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
-   [UShort \(Tipo de datos\)](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 Al aplicar <xref:System.CLSCompliantAttribute> a un elemento de programación, se establece el parámetro `isCompliant` del atributo en `True` o `False` para indicar compatibilidad o incompatibilidad.  No hay ningún valor predeterminado para este parámetro por lo que debe proporcionar uno.  
  
 Si no se aplica <xref:System.CLSCompliantAttribute> a un elemento, se considerará que no es compatible.  
  
 De forma predeterminada, este mensaje es una advertencia.  Para obtener más información sobre cómo ocultar las advertencias o tratarlas como errores, vea [Configurar advertencias en Visual Basic](/visual-studio/ide/configuring-warnings-in-visual-basic).  
  
 **Identificador de error:** BC40027  
  
### Para corregir este error  
  
-   Si el procedimiento `Function` debe devolver este tipo determinado, quite el <xref:System.CLSCompliantAttribute>.  El procedimiento no puede ser conforme a CLS.  
  
-   Si el procedimiento `Function` debe ser conforme a CLS, cambie el tipo de valor devuelto al tipo conforme a CLS más próximo.  Por ejemplo, si no necesita el intervalo de valores por encima de 2.147.483.647, tal vez pueda utilizar `Integer` en lugar de `UInteger`.  Si necesita el intervalo extendido, puede reemplazar `UInteger` por `Long`.  
  
-   Si crea una interfaz con objetos de automatización o COM, tenga en cuenta que algunos tipos tienen anchos de datos distintos que en [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)].  Por ejemplo, `int` suele ser de 16 bits en otros entornos.  Al devolver un entero de 16 bits a esos componentes, declárelo como `Short` en lugar de como `Integer` en el código administrado de [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)].  
  
## Vea también  
 [\<PAVE OVER\> Writing CLS\-Compliant Code](http://msdn.microsoft.com/es-es/4c705105-69a2-4e5e-b24e-0633bc32c7f3)