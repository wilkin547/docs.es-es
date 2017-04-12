---
title: "Introducción a la interoperabilidad COM (Visual Basic) | Documentos de Microsoft"
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
- interop assemblies
- COM interop, about COM interop
ms.assetid: 8bd62e68-383d-407f-998b-29aa0ce0fd67
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
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
ms.openlocfilehash: 8866dbadca040c57ed2b59540dd2c341eb81758c
ms.lasthandoff: 03/13/2017

---
# <a name="introduction-to-com-interop-visual-basic"></a>Información general sobre la interoperabilidad COM (Visual Basic)
El modelo de objetos componentes (COM) permite a un objeto exponer su funcionalidad a otros componentes y aplicaciones host. Aunque los objetos COM han sido fundamentales para Windows durante muchos años de programación, las aplicaciones diseñadas para common language runtime (CLR) proporcionan muchas ventajas.  
  
 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)]aplicaciones reemplazará finalmente las desarrolladas con COM. Hasta entonces, tendrá que utilizar o crear objetos COM mediante [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)]. Interoperabilidad con COM, o *interoperabilidad COM*, le permite utilizar objetos COM existentes mientras realiza la transición a la [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] a su propio ritmo.  
  
 Mediante el uso de la [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] para crear componentes COM, puede utilizar la interoperabilidad COM sin registro. Esto le permite controlar qué versión del archivo DLL se habilita cuando se instala en un equipo más de una versión y permite a los usuarios finales utilizar XCOPY o FTP para copiar la aplicación en un directorio adecuado en el equipo donde se puede ejecutar. Para obtener más información, consulte [interoperabilidad COM sin registro](http://msdn.microsoft.com/library/90f308b9-82dc-414a-bce1-77e0155e56bd).  
  
## <a name="managed-code-and-data"></a>Código administrado y datos  
 Código desarrollado para el [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] se conoce como *código administrado*y contiene metadatos que usan CLR. Los datos utilizados por [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] aplicaciones se llama *datos administrados* porque el runtime administra tareas relacionadas con datos, como asignación y recuperación de memoria y realizar la comprobación de tipos. De forma predeterminada, [!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong_md.md)] utiliza código administrado y datos, pero puede tener acceso a los datos de objetos COM mediante ensamblados de interoperabilidad (descritos más adelante en esta página) y el código no administrado.  
  
## <a name="assemblies"></a>Ensamblados  
 Un ensamblado es el principal bloque de creación de un [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] aplicación. Es una colección de funciones que se genera, versiones e implementado como una sola unidad de implementación que contiene uno o más archivos. Cada ensamblado contiene un manifiesto del ensamblado.  
  
## <a name="type-libraries-and-assembly-manifests"></a>Bibliotecas de tipos y manifiestos de ensamblado  
 Bibliotecas de tipos describen las características de objetos COM, como nombres de miembros y tipos de datos. Manifiestos de ensamblado realizan la misma función de [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] aplicaciones. Incluyen información acerca de lo siguiente:  
  
-   Identidad del ensamblado, versión, referencia cultural y firma digital.  
  
-   Archivos que componen la implementación del ensamblado.  
  
-   Tipos y recursos que componen el ensamblado. Esto incluye aquellas que se exportan desde.  
  
-   Dependencias de tiempo de compilación en otros ensamblados.  
  
-   Permisos necesarios para que el ensamblado se ejecute correctamente.  
  
 Para obtener más información sobre ensamblados y manifiestos de ensamblado, consulte [ensamblados y la caché de ensamblados Global](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md).  
  
### <a name="importing-and-exporting-type-libraries"></a>Importación y exportación de bibliotecas de tipos  
 [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)]contiene una utilidad, Tlbimp, que le permite importar información desde una biblioteca de tipos en un [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] aplicación. Puede generar bibliotecas de tipos de ensamblados mediante la utilidad Tlbexp.  
  
 Para obtener información sobre Tlbimp y Tlbexp, consulte [Tlbimp.exe (importador de la biblioteca de tipos)](http://msdn.microsoft.com/library/ec0a8d63-11b3-4acd-b398-da1e37e97382) y [Tlbexp.exe (exportador de la biblioteca de tipos)](http://msdn.microsoft.com/library/a487d61b-d166-467b-a7ca-d8b52fbff42d).  
  
## <a name="interop-assemblies"></a>Ensamblados de interoperabilidad  
 Ensamblados de interoperabilidad son [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] ensamblados que puente entre administrado y código, miembros de objetos COM de asignación equivalente [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] miembros administrados. Ensamblados de interoperabilidad creados por [!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong_md.md)] controlar muchos de los detalles del trabajo con objetos COM, como el cálculo de referencias de interoperabilidad.  
  
## <a name="interoperability-marshaling"></a>Cálculo de referencias de interoperabilidad  
 Todos los [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] aplicaciones comparten un conjunto de tipos comunes que permiten la interoperabilidad de objetos, independientemente del lenguaje de programación que se utiliza. Los parámetros y valores devueltos de los objetos COM a veces utilizan tipos de datos que difieren de aquéllos utilizados en código administrado. *Cálculo de referencias de interoperabilidad* es el proceso de empaquetado de parámetros y valores devueltos en tipos de datos equivalentes enviados a y desde objetos COM. Para obtener más información, consulte [interoperativo](http://msdn.microsoft.com/library/115f7a2f-d422-4605-ab36-13a8dd28142a).  
  
## <a name="see-also"></a>Vea también  
 [Interoperabilidad COM](../../../visual-basic/programming-guide/com-interop/index.md)   
 [Tutorial: Implementar la herencia mediante objetos COM](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)   
 [Interoperación con código no administrado](https://msdn.microsoft.com/library/sd10k43k)   
 [Solucionar problemas de interoperabilidad](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)   
 [Ensamblados y caché Global de ensamblados](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)   
 [Tlbimp.exe (importador de la biblioteca de tipos)](http://msdn.microsoft.com/library/ec0a8d63-11b3-4acd-b398-da1e37e97382)   
 [Tlbexp.exe (exportador de la biblioteca de tipos)](http://msdn.microsoft.com/library/a487d61b-d166-467b-a7ca-d8b52fbff42d)   
 [Cálculo de referencias de interoperabilidad](http://msdn.microsoft.com/library/115f7a2f-d422-4605-ab36-13a8dd28142a)   
 [Interoperabilidad COM sin registro](http://msdn.microsoft.com/library/90f308b9-82dc-414a-bce1-77e0155e56bd)
