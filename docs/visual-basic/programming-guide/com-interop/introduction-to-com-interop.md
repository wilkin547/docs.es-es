---
title: "Informaci&#243;n general sobre la interoperabilidad COM (Visual Basic) | Microsoft Docs"
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
  - "interoperabilidad COM, acerca de la interoperabilidad COM"
  - "ensamblados de interoperabilidad"
ms.assetid: 8bd62e68-383d-407f-998b-29aa0ce0fd67
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Informaci&#243;n general sobre la interoperabilidad COM (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

El Modelo de objetos componentes \(COM\) permite a un objeto exponer su funcionalidad a otros componentes y aplicaciones host.  Aunque los objetos COM han sido fundamentales para la programación para Windows durante muchos años, las aplicaciones diseñadas para Common Language Runtime \(CLR\) proporcionan muchas ventajas.  
  
 Las aplicaciones de [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] terminarán por reemplazar a las aplicaciones desarrolladas con COM.  Hasta entonces, es posible que deba utilizar o crear objetos COM mediante [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)].  La interoperabilidad con COM, o *interoperabilidad COM*, le permite utilizar objetos COM existentes mientras realiza la transición a [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] a su propio ritmo.  
  
 Al utilizar [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] para crear componentes COM, puede usar la interoperabilidad COM sin necesidad de registrarse.  Esto le permite controlar qué versión del archivo DLL se habilita cuando hay instalada más de una versión en un equipo y permite a los usuarios finales utilizar XCOPY o FTP para copiar la aplicación en un directorio adecuado de su equipo donde se pueda ejecutar.  Para obtener más información, vea [Registration\-Free COM Interop](../Topic/Registration-Free%20COM%20Interop.md).  
  
## Código administrado y datos administrados  
 El código desarrollado para [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] se denomina *código administrado* y contiene metadatos que utiliza Common Language Runtime \(CLR\).  Los datos utilizados por las aplicaciones de [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] se denominan *datos administrados* porque las tareas relacionadas con datos, como asignación y recuperación de memoria y comprobación de tipos se administran en tiempo de ejecución.  De forma predeterminada, [!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong_md.md)] utiliza código y datos administrados, pero puede tener acceso al código no administrado y a los datos de objetos COM que utilizan ensamblados de interoperabilidad \(esto se describe más adelante en esta página\).  
  
## Ensamblados  
 Un ensamblado es el bloque de creación principal de una aplicación de [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)].  Es un conjunto de características de funcionalidad que se compila, recibe un número de versión y se implanta como una sola unidad de implementación que contiene uno o más archivos.  Cada ensamblado contiene un manifiesto del ensamblado.  
  
## Bibliotecas de tipos y manifiestos del ensamblado  
 Las bibliotecas de tipos describen las características de los objetos COM, como los nombres de miembro y los tipos de datos.  Los manifiestos del ensamblado realizan esta misma función para aplicaciones de [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)].  Incluyen información sobre lo siguiente:  
  
-   Identidad, versión, referencia cultural y firma digital del ensamblado.  
  
-   Archivos que componen la implementación de un ensamblado.  
  
-   Tipos y recursos de los que consta el ensamblado.  Esto incluye aquéllos que se exportan de él.  
  
-   Dependencias de tiempo de compilación en otros ensamblados.  
  
-   Permisos requeridos para que el ensamblado se ejecute correctamente.  
  
 Para obtener más información sobre ensamblados y manifiestos del ensamblado, vea [Ensamblados y Caché global de ensamblados](../Topic/Assemblies%20and%20the%20Global%20Assembly%20Cache%20\(C%23%20and%20Visual%20Basic\).md).  
  
### Importar y exportar las bibliotecas de tipos  
 [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] contiene una utilidad, Tlbimp, que le permite importar información de una biblioteca de tipos a una aplicación de [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)].  Puede generar bibliotecas de tipos a partir de ensamblados mediante la utilidad Tlbexp.  
  
 Para obtener información sobre Tlbimp y Tlbexp, vea [Tlbimp.exe \(Type Library Importer\)](../Topic/Tlbimp.exe%20\(Type%20Library%20Importer\).md) y [Tlbexp.exe \(Type Library Exporter\)](../Topic/Tlbexp.exe%20\(Type%20Library%20Exporter\).md).  
  
## Ensamblados de interoperabilidad  
 Los ensamblados de interoperabilidad son ensamblados de [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] que actúan como puentes entre el código administrado y el no administrado, y asignan miembros de objetos COM a los miembros administrados equivalentes de [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)].  Los ensamblados de interoperabilidad creados en [!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong_md.md)] controlan muchos de los detalles del trabajo con objetos COM, como el cálculo de referencias de interoperabilidad.  
  
## Cálculo de referencias de interoperabilidad  
 Todas las aplicaciones de [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] comparten un conjunto de tipos comunes que permiten la interoperabilidad de objetos, independientemente del lenguaje de programación que se utilice.  A veces, los parámetros de los objetos COM y los valores devueltos utilizan tipos de datos distintos de los que se utilizan en el código administrado.  El *cálculo de referencias de interoperabilidad* es el proceso de empaquetar parámetros y valores devueltos en tipos de datos equivalentes enviados a \(o recibidos de\) objetos COM.  Para obtener más información, vea [Interop Marshaling](../Topic/Interop%20Marshaling.md).  
  
## Vea también  
 [Interoperabilidad COM](../../../visual-basic/programming-guide/com-interop/index.md)   
 [Tutorial: Implementar la herencia mediante objetos COM](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)   
 [Interoperating with Unmanaged Code](../Topic/Interoperating%20with%20Unmanaged%20Code.md)   
 [Solución de problemas de interoperabilidad](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)   
 [Ensamblados y Caché global de ensamblados](../Topic/Assemblies%20and%20the%20Global%20Assembly%20Cache%20\(C%23%20and%20Visual%20Basic\).md)   
 [Tlbimp.exe \(Type Library Importer\)](../Topic/Tlbimp.exe%20\(Type%20Library%20Importer\).md)   
 [Tlbexp.exe \(Type Library Exporter\)](../Topic/Tlbexp.exe%20\(Type%20Library%20Exporter\).md)   
 [Interop Marshaling](../Topic/Interop%20Marshaling.md)   
 [Registration\-Free COM Interop](../Topic/Registration-Free%20COM%20Interop.md)