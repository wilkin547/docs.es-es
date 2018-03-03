---
title: Comentarios de la Comunidad WPF
ms.date: 03/01/2018
ms.prod: .net-framework
ms.technology:
- dotnet-wpf
ms.topic: article
helpviewer_keywords:
- community resources [WPF]
- forums [WPF]
- bug descriptions [WPF]
ms.assetid: 468b060a-d54b-4900-a74a-9faccb554045
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 243e40b1b16fd88a786398c15cd29a5baeacd6ac
ms.sourcegitcommit: ba765893e3efcece67d99fd6d5ce0074b050d1d9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/02/2018
---
# <a name="wpf-community-feedback"></a>Comentarios de la Comunidad WPF

Microsoft ofrece una amplia gama de recursos de la Comunidad para que pueda conocer, analizar y proporcionar comentarios sobre Windows Presentation Foundation (WPF). Estos recursos incluyen foros y [Comunidad de desarrolladores de Visual Studio](https://developercommunity.visualstudio.com/) sitio. Cada recurso de comunidad proporciona un conjunto diferente de ventajas. Estas ventajas se describen aquí, así como un conjunto de prácticas recomendadas para utilizar cada uno de ellos para asegurarse la mejor respuesta de la Comunidad a gran y Microsoft en particular.

> [!NOTE]
> No use la sección de comentarios situada en la parte inferior de cada página para enviar comentarios sobre el producto. Estos vínculos son solo para comentarios sobre la documentación.

## <a name="forums"></a>Foros

El [foro WPF](https://social.msdn.microsoft.com/Forums/vstudio/en-US/home?forum=wpf) es el recurso principal de comunidad para analizar y solucionar problemas. Los foros facilitan el debate y la resolución de problemas al ofrecer un conjunto completo de características de compatibilidad que incluyen:

- Búsqueda.
- Seguimiento de debates.
- Formato enriquecido para texto y código.
- Integración de Visual Studio.
- Implicación de los profesionales más valiosos (MVP) y de la comunidad.
- Supervisión para asegurarse de que las publicaciones se responden en el menor tiempo posible.

Otra opción que permite realizar preguntas a la Comunidad sobre WPF es [desbordamiento de la pila](https://stackoverflow.com/questions/tagged/wpf).

### <a name="forum-best-practices"></a>Prácticas recomendadas de foro

Uso de las siguientes categorías de prácticas ayuda a resolver problemas publicados en el foro de WPF en el menor tiempo posible. Estos procedimientos se aplican a todos los foros.

#### <a name="search-existing-posts"></a>Buscar envíos existentes

Algunos problemas se producen con tanta frecuencia que otras personas ya se han enfrentado antes a ellos. Por consiguiente, puede resolver el problema rápidamente, o puede agregar su entrada a una discusión existente.

#### <a name="use-meaningful-titles"></a>Utilizar títulos significativos

Títulos concisos, significativos mejoran la detectabilidad de sus publicaciones. También resultará más fácil para otros miembros de la Comunidad WPF foro determinar si puede resolver el problema.

#### <a name="include-appropriate-content"></a>Incluir el contenido adecuado

Describa el problema y cómo se probó para que funcione a través de él. Si es posible, incluya fragmentos de código adicionales o el ejemplo más sencillo posible que muestre el problema. Todos estos detalles contribuyen a aumentar las posibilidades de que su pregunta se responda rápidamente.

## <a name="visual-studio-developer-community"></a>Comunidad de desarrolladores de Visual Studio

A veces los problemas pueden ser difíciles de resolver o irresolubles. Tales situaciones se presentan debido a errores de tecnología, dificultades para aplicar la tecnología a escenarios determinados o a la falta de compatibilidad con escenarios concretos. Esta información es importante para Microsoft y puede proporcionarse a través de la [Comunidad de desarrolladores de Visual Studio](https://developercommunity.visualstudio.com/) sitio.

Elementos publicados en el centro de comentarios del producto de WPF se enrutan a la base de datos de error interno del equipo WPF. Por consiguiente, es la manera más confiable de obtener sus comentarios al propietario de la característica WPF. Además, puede validar y realizar un seguimiento de errores y sugerencias, así como votar sobre ellas, lo que ayuda al equipo WPF a priorizar los problemas.

### <a name="developer-community-best-practices"></a>Recomendaciones para la Comunidad de desarrolladores

Al enviar a la Comunidad de desarrolladores de Visual Studio, Buscar envíos existentes, proporcionar un título significativo y contenido adecuado son algunas recomendaciones importantes, tal como aparecen para el registro en el foro de WPF. A continuación se muestran los procedimientos recomendados adicionales que también debería emplear.

#### <a name="search-existing-posts"></a>Buscar envíos existentes

Algunos problemas se producen con tanta frecuencia que otras personas ya se han enfrentado antes a ellos. Por lo tanto, puede resolver el problema rápidamente, o puede agregar la entrada a un problema existente.

#### <a name="use-meaningful-titles"></a>Utilizar títulos significativos

Aumento de títulos conciso y significativo la posibilidad de que el problema se dirija al equipo de WPF más adecuado en la menor cantidad de tiempo. Esto es especialmente importante para una tecnología como WPF, que contiene muchas características interrelacionadas.

#### <a name="describe-how-to-reproduce-your-bug"></a>Describe cómo reproducir el error

Al publicar sobre un error, es importante incluir lo siguiente cuando corresponda:

- Proporcione una descripción clara del error.
- Utilice fragmentos de código para respaldar la descripción del error.
- Proporcione una lista de pasos que muestren cómo reproducir el error.
- Incluya el código de ejemplo más pequeño posible que reproduzca el error.
- Mencione si el error se puede reproducir consistentemente o no.
- Incluya la información de excepciones pertinente.

 Si el error está relacionado con la instalación o configuración, adjunte los registros de instalación pertinentes y las instantáneas (archivos prefijados con "dd_" que se encuentran en la carpeta %temp%).

 En el caso de problemas de compilación, adjunte los registros de compilación. El sistema puede configurarse para de MSBuild admite el registro con diferentes niveles de detalle con el modificador/v: desde la línea de comandos o configurando el nivel adecuado de un entorno de desarrollo integrado (IDE) como Visual Studio.

#### <a name="provide-environment-information"></a>Proporcionar información de entorno

La información general puede resultar útil para agregar contexto a su publicación. En particular, mencione la plataforma del sistema operativo, la familia de procesadores y la arquitectura, por ejemplo, "Windows 10 versión 1709, Intel (r) Xeon (r), x64."

Si el problema que está publicando está relacionado con la representación, también debe incluir detalles de tarjeta y del controlador de gráficos, si es posible. Esta información es importante porque WPF es un marco de presentación.

#### <a name="provide-solution-or-project-information"></a>Proporciona información de solución o proyecto

Los errores pueden pertenecer a las herramientas utilizadas para desarrollar y compilar las aplicaciones y los tipos de aplicaciones que se va a compilar. Por lo tanto, puede ser útil especificar:

- El tipo de aplicación que está creando, como:
  - Aplicación (*.exe*) o una biblioteca (*.dll*)
  - Aplicación de explorador extensible de lenguaje de marcado de aplicaciones (XAML) (XBAP)
  - Flexible de las aplicaciones XAML
  - Aplicaciones independientes instalado
  - Aplicaciones independientes implementadas por ClickOnce
- La herramienta de desarrollo, como:
  - MSBuild
  - Diseñador gráfico de expresión
  - Diseñador interactivo de expresión
  - Programa para la mejora
- La configuración de soluciones, como:
  - Una solución
  - Un solo proyecto
  - Una solución con varios proyectos dependientes
- Si la aplicación tiene recursos neutrales o específicos del idioma. Por ejemplo, ¿especificó la propiedad del proyecto `UICulture` o metadatos localizables para los tipos `Application`, `Page` y `Resource`?
- Si utilizó la configuración neutral de idioma en el archivo AssemblyInfo.cs o AssemblyInfo.vb.

#### <a name="provide-scenario-and-impact-information"></a>Proporcionar información de escenario y del impacto

Proporciona información sobre el escenario que se manifiesta el error y su impacto. Esta información es muy importante al equipo de WPF cuando decide si, cuándo y cómo se debe corregir un problema, o si se puede utilizar una solución aceptable en su lugar.

Normalmente, los escenarios de pérdida de datos y bloqueo son de alto impacto y, por lo tanto, los más fáciles para establecer prioridades. Sin embargo, algunos errores solo aparecen en escenarios poco comunes, que también pueden ser los escenarios principales en algunos casos. Proporcionar un contexto del escenario y del impacto ayuda al equipo WPF a tomar la decisión correcta.

## <a name="see-also"></a>Vea también

[Cómo notificar un problema con Visual Studio 2017](/visualstudio/ide/how-to-report-a-problem-with-visual-studio-2017)
