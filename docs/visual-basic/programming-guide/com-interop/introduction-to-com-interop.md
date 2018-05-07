---
title: Información general sobre la interoperabilidad COM (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- interop assemblies
- COM interop [Visual Basic], about COM interop
ms.assetid: 8bd62e68-383d-407f-998b-29aa0ce0fd67
ms.openlocfilehash: 639b621215f25bc1042274a92a21fca2985e5918
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="introduction-to-com-interop-visual-basic"></a>Información general sobre la interoperabilidad COM (Visual Basic)
El modelo de objetos componentes (COM) permite a un objeto exponer su funcionalidad a otros componentes y aplicaciones del host. Aunque los objetos COM han sido fundamentales para la programación durante muchos años para Windows, las aplicaciones diseñadas para common language runtime (CLR) ofrecen muchas ventajas.  
  
 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] las aplicaciones reemplazará finalmente a los que haya creado con COM. Hasta entonces, tendrá que utilizar o crear objetos COM con Visual Studio. Interoperabilidad con COM, o *interoperabilidad COM*, le permite utilizar objetos COM existentes mientras realiza la transición a la [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] a su propio ritmo.  
  
 Mediante el uso de la [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] para crear componentes COM, puede usar la interoperabilidad COM sin registro. Esto le permite controlar qué versión del archivo DLL se habilita cuando se instala en un equipo más de una versión y permite a los usuarios finales utilizar XCOPY o FTP para copiar la aplicación en un directorio adecuado en su equipo en el que se ejecuta. Para obtener más información, consulte [interoperabilidad COM sin registro](http://msdn.microsoft.com/library/90f308b9-82dc-414a-bce1-77e0155e56bd).  
  
## <a name="managed-code-and-data"></a>Código administrado y datos  
 Código desarrollado para la [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] se conoce como *código administrado*y contiene metadatos que utilizan el CLR. Los datos utilizados por [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] aplicaciones se denominan *datos administrados* porque el tiempo de ejecución encarga de tareas relacionadas con datos, como asignación y recuperación de memoria y realizar la comprobación de tipos. De forma predeterminada, Visual Basic .NET usa código administrado y los datos, pero puede tener acceso a código no administrado y datos de objetos COM mediante ensamblados de interoperabilidad (descritos más adelante en esta página).  
  
## <a name="assemblies"></a>Ensamblados  
 Un ensamblado es el principal bloque de creación de un [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] aplicación. Es una colección de funcionalidad que está compilado, con control de versiones e implementado como una sola unidad de implementación que contiene uno o varios archivos. Cada ensamblado contiene un manifiesto del ensamblado.  
  
## <a name="type-libraries-and-assembly-manifests"></a>Bibliotecas de tipos y manifiestos de ensamblado  
 Bibliotecas de tipos describen las características de objetos COM, como nombres de miembros y tipos de datos. Manifiestos de ensamblado realizan la misma función de [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] las aplicaciones. Incluyen información acerca de lo siguiente:  
  
-   Identidad del ensamblado, versión, referencia cultural y firma digital.  
  
-   Archivos que componen la implementación del ensamblado.  
  
-   Los tipos y recursos que componen el ensamblado. Esto incluye aquellas que se exportan desde él.  
  
-   Dependencias de tiempo de compilación en otros ensamblados.  
  
-   Permisos necesarios para que el ensamblado que se ejecuten correctamente.  
  
 Para obtener más información sobre los ensamblados y manifiestos de ensamblado, consulte [ensamblados y la caché Global de ensamblados](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md).  
  
### <a name="importing-and-exporting-type-libraries"></a>Importación y exportación de bibliotecas de tipos  
 Visual Studio contiene una utilidad, Tlbimp, que le permite importar información desde una biblioteca de tipos en un [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] aplicación. Puede generar las bibliotecas de tipos de los ensamblados mediante la utilidad Tlbexp.  
  
 Para obtener información sobre Tlbimp y Tlbexp, vea [Tlbimp.exe (importador de la biblioteca de tipos)](../../../framework/tools/tlbimp-exe-type-library-importer.md) y [Tlbexp.exe (exportador de la biblioteca de tipos)](http://msdn.microsoft.com/library/a487d61b-d166-467b-a7ca-d8b52fbff42d).  
  
## <a name="interop-assemblies"></a>Ensamblados de interoperabilidad  
 Ensamblados de interoperabilidad son [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] ensamblados que puente entre administrado y código, los miembros de objeto de asignación COM a equivalente [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] miembros administrados. Ensamblados de interoperabilidad creados mediante Visual Basic .NET controlan muchos de los detalles sobre cómo trabajar con objetos COM, como el cálculo de referencias de interoperabilidad.  
  
## <a name="interoperability-marshaling"></a>Cálculo de referencias de interoperabilidad  
 Todos los [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] aplicaciones comparten un conjunto de tipos comunes que permiten la interoperabilidad de objetos, independientemente del lenguaje de programación que se utiliza. Los parámetros y valores devueltos de los objetos COM a veces, utilizan tipos de datos que difieren de aquéllos utilizados en código administrado. *Cálculo de referencias de interoperabilidad* es el proceso de empaquetado de parámetros y valores devueltos en tipos de datos equivalentes de medida que se mueven hacia y desde objetos COM. Para obtener más información, consulte [cálculo de referencias interoperativo](../../../framework/interop/interop-marshaling.md).  
  
## <a name="see-also"></a>Vea también  
 [Interoperabilidad COM](../../../visual-basic/programming-guide/com-interop/index.md)  
 [Tutorial: Implementación de la herencia mediante objetos COM](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)  
 [Interoperating with Unmanaged Code](../../../framework/interop/index.md) (Interoperar con código no administrado)  
 [Solución de problemas de interoperabilidad](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)  
 [Ensamblados y Caché global de ensamblados](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [TlbImp.exe (Importador de la biblioteca de tipos)](../../../framework/tools/tlbimp-exe-type-library-importer.md)  
 [Tlbexp.exe (Exportador de la biblioteca de tipos)](http://msdn.microsoft.com/library/a487d61b-d166-467b-a7ca-d8b52fbff42d)  
 [Serialización de interoperabilidad](../../../framework/interop/interop-marshaling.md)  
 [Interoperabilidad COM sin registro](http://msdn.microsoft.com/library/90f308b9-82dc-414a-bce1-77e0155e56bd)
