---
title: Ampliar el marco de vidrio en una aplicación de WPF
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- applications [WPF], extending glass frames into
- graphics [WPF], extending glass frames into applications
- extending glass frames into applications [WPF]
- glass frames [WPF], extending into applications
ms.assetid: 74388a3a-4b69-4a9d-ba1f-e107636bd660
ms.openlocfilehash: 93eda6d6a13d6a510f2aeb06ab1c66d0cd40927f
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43556423"
---
# <a name="extend-glass-frame-into-a-wpf-application"></a><span data-ttu-id="ec344-102">Ampliar el marco de vidrio en una aplicación de WPF</span><span class="sxs-lookup"><span data-stu-id="ec344-102">Extend Glass Frame Into a WPF Application</span></span>
<span data-ttu-id="ec344-103">En este tema muestra cómo extender el [!INCLUDE[TLA#tla_winvista](../../../../includes/tlasharptla-winvista-md.md)] marco de vidrio en el área de cliente de una aplicación de Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="ec344-103">This topic demonstrates how to extend the [!INCLUDE[TLA#tla_winvista](../../../../includes/tlasharptla-winvista-md.md)] glass frame into the client area of a Windows Presentation Foundation (WPF) application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ec344-104">Este ejemplo solo funciona en una máquina [!INCLUDE[TLA2#tla_winvista](../../../../includes/tla2sharptla-winvista-md.md)] que ejecute el Administrador de ventanas de escritorio (DWM) con efecto de cristal habilitado.</span><span class="sxs-lookup"><span data-stu-id="ec344-104">This example will only work on a [!INCLUDE[TLA2#tla_winvista](../../../../includes/tla2sharptla-winvista-md.md)] machine running the Desktop Window Manager (DWM) with glass enabled.</span></span> [!INCLUDE[TLA2#tla_winvista](../../../../includes/tla2sharptla-winvista-md.md)]<span data-ttu-id="ec344-105"> Home Basic no admite el efecto de cristal transparente.</span><span class="sxs-lookup"><span data-stu-id="ec344-105"> Home Basic edition does not support the transparent glass effect.</span></span> <span data-ttu-id="ec344-106">Las áreas que normalmente se representarían con el efecto de cristal transparente en otras ediciones de [!INCLUDE[TLA2#tla_winvista](../../../../includes/tla2sharptla-winvista-md.md)] se representan opacas.</span><span class="sxs-lookup"><span data-stu-id="ec344-106">Areas that would typically render with the transparent glass effect on other editions of [!INCLUDE[TLA2#tla_winvista](../../../../includes/tla2sharptla-winvista-md.md)] are rendered opaque.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ec344-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ec344-107">Example</span></span>  
 <span data-ttu-id="ec344-108">En la siguiente imagen se muestra el marco de vidrio ampliado en la barra de direcciones de Internet Explorer 7.</span><span class="sxs-lookup"><span data-stu-id="ec344-108">The following image illustrates the glass frame extended into the address bar of Internet Explorer 7.</span></span>  
  
 <span data-ttu-id="ec344-109">**Internet Explorer con marco de cristal ampliado detrás de la barra de direcciones.**</span><span class="sxs-lookup"><span data-stu-id="ec344-109">**Internet Explorer with extended glass frame behind address bar.**</span></span>  
  
 <span data-ttu-id="ec344-110">![IE7 con marco de cristal ampliado detrás de la barra de direcciones.](../../../../docs/framework/wpf/graphics-multimedia/media/ie7glasstopbar.PNG "IE7glasstopbar")</span><span class="sxs-lookup"><span data-stu-id="ec344-110">![IE7 with glass frame extended behind address bar.](../../../../docs/framework/wpf/graphics-multimedia/media/ie7glasstopbar.PNG "IE7glasstopbar")</span></span>  
  
 <span data-ttu-id="ec344-111">Para ampliar el marco de cristal en una aplicación [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] se requiere acceso a la [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] no administrada.</span><span class="sxs-lookup"><span data-stu-id="ec344-111">To extend the glass frame on a [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] application, access to unmanaged [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] is needed.</span></span> <span data-ttu-id="ec344-112">El siguiente ejemplo de código realiza una invocación de plataforma (pinvoke) para las dos [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] necesarias para ampliar el marco en el área cliente.</span><span class="sxs-lookup"><span data-stu-id="ec344-112">The following code example does a Platform Invoke (pinvoke) for the two [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] needed to extend the frame into the client area.</span></span> <span data-ttu-id="ec344-113">Cada una de estas [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] se declaran en una clase denominada **NonClientRegionAPI**.</span><span class="sxs-lookup"><span data-stu-id="ec344-113">Each of these [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] are declared in a class called **NonClientRegionAPI**.</span></span>  
  
```csharp  
[StructLayout(LayoutKind.Sequential)]  
public struct MARGINS  
{  
    public int cxLeftWidth;      // width of left border that retains its size  
    public int cxRightWidth;     // width of right border that retains its size  
    public int cyTopHeight;      // height of top border that retains its size  
    public int cyBottomHeight;   // height of bottom border that retains its size  
};  
  
[DllImport("DwmApi.dll")]  
public static extern int DwmExtendFrameIntoClientArea(  
    IntPtr hwnd,  
    ref MARGINS pMarInset);  
```  
  
```vb  
<StructLayout(LayoutKind.Sequential)>  
        Public Structure MARGINS  
            Public cxLeftWidth As Integer ' width of left border that retains its size  
            Public cxRightWidth As Integer ' width of right border that retains its size  
            Public cyTopHeight As Integer ' height of top border that retains its size  
            Public cyBottomHeight As Integer ' height of bottom border that retains its size  
        End Structure  
  
        <DllImport("DwmApi.dll")>  
        Public Shared Function DwmExtendFrameIntoClientArea(ByVal hwnd As IntPtr, ByRef pMarInset As MARGINS) As Integer  
        End Function  
```  
  
 <span data-ttu-id="ec344-114">[DwmExtendFrameIntoClientArea](/windows/desktop/api/dwmapi/nf-dwmapi-dwmextendframeintoclientarea) es la función de DWM que amplia el marco en el área cliente.</span><span class="sxs-lookup"><span data-stu-id="ec344-114">[DwmExtendFrameIntoClientArea](/windows/desktop/api/dwmapi/nf-dwmapi-dwmextendframeintoclientarea) is the DWM function that extends the frame into the client area.</span></span> <span data-ttu-id="ec344-115">Toma dos parámetros; un identificador de ventana y una estructura [MARGINS](/windows/desktop/api/uxtheme/ns-uxtheme-_margins).</span><span class="sxs-lookup"><span data-stu-id="ec344-115">It takes two parameters; a window handle and a [MARGINS](/windows/desktop/api/uxtheme/ns-uxtheme-_margins) structure.</span></span> <span data-ttu-id="ec344-116">[MARGINS](/windows/desktop/api/uxtheme/ns-uxtheme-_margins) se usa para indicarle al DWM cuánto más debe ampliarse el marco en el área cliente.</span><span class="sxs-lookup"><span data-stu-id="ec344-116">[MARGINS](/windows/desktop/api/uxtheme/ns-uxtheme-_margins) is used to tell the DWM how much extra the frame should be extended into the client area.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ec344-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ec344-117">Example</span></span>  
 <span data-ttu-id="ec344-118">Para usar la función [DwmExtendFrameIntoClientArea](/windows/desktop/api/dwmapi/nf-dwmapi-dwmextendframeintoclientarea), debe obtenerse un identificador de ventana.</span><span class="sxs-lookup"><span data-stu-id="ec344-118">To use the [DwmExtendFrameIntoClientArea](/windows/desktop/api/dwmapi/nf-dwmapi-dwmextendframeintoclientarea) function, a window handle must be obtained.</span></span> <span data-ttu-id="ec344-119">En [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], se puede obtener el identificador de ventana de la <xref:System.Windows.Interop.HwndSource.Handle%2A> propiedad de un <xref:System.Windows.Interop.HwndSource>.</span><span class="sxs-lookup"><span data-stu-id="ec344-119">In [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], the window handle can be obtained from the <xref:System.Windows.Interop.HwndSource.Handle%2A> property of an <xref:System.Windows.Interop.HwndSource>.</span></span> <span data-ttu-id="ec344-120">En el ejemplo siguiente, el marco se extiende en el área de cliente en el <xref:System.Windows.FrameworkElement.Loaded> eventos de la ventana.</span><span class="sxs-lookup"><span data-stu-id="ec344-120">In the following example, the frame is extended into the client area on the <xref:System.Windows.FrameworkElement.Loaded> event of the window.</span></span>  
  
```csharp  
void OnLoaded(object sender, RoutedEventArgs e)  
{  
   try  
   {  
      // Obtain the window handle for WPF application  
      IntPtr mainWindowPtr = new WindowInteropHelper(this).Handle;  
      HwndSource mainWindowSrc = HwndSource.FromHwnd(mainWindowPtr);  
      mainWindowSrc.CompositionTarget.BackgroundColor = Color.FromArgb(0, 0, 0, 0);  
  
      // Get System Dpi  
      System.Drawing.Graphics desktop = System.Drawing.Graphics.FromHwnd(mainWindowPtr);  
      float DesktopDpiX = desktop.DpiX;  
      float DesktopDpiY = desktop.DpiY;  
  
      // Set Margins  
      NonClientRegionAPI.MARGINS margins = new NonClientRegionAPI.MARGINS();  
  
      // Extend glass frame into client area  
      // Note that the default desktop Dpi is 96dpi. The  margins are  
      // adjusted for the system Dpi.  
      margins.cxLeftWidth = Convert.ToInt32(5 * (DesktopDpiX / 96));  
      margins.cxRightWidth = Convert.ToInt32(5 * (DesktopDpiX / 96));  
      margins.cyTopHeight = Convert.ToInt32(((int)topBar.ActualHeight + 5) * (DesktopDpiX / 96));  
      margins.cyBottomHeight = Convert.ToInt32(5 * (DesktopDpiX / 96));  
  
      int hr = NonClientRegionAPI.DwmExtendFrameIntoClientArea(mainWindowSrc.Handle, ref margins);  
      //  
      if (hr < 0)  
      {  
         //DwmExtendFrameIntoClientArea Failed  
      }  
   }  
   // If not Vista, paint background white.  
   catch (DllNotFoundException)  
   {  
      Application.Current.MainWindow.Background = Brushes.White;  
   }  
}  
```  
  
## <a name="example"></a><span data-ttu-id="ec344-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ec344-121">Example</span></span>  
 <span data-ttu-id="ec344-122">En el ejemplo siguiente se muestra una ventana simple en la que el marco se amplía en el área cliente.</span><span class="sxs-lookup"><span data-stu-id="ec344-122">The following example shows a simple window in which the frame is extended into the client area.</span></span> <span data-ttu-id="ec344-123">El marco se amplía por detrás del borde superior que contiene las dos <xref:System.Windows.Controls.TextBox> objetos.</span><span class="sxs-lookup"><span data-stu-id="ec344-123">The frame is extended behind the top border that contains the two <xref:System.Windows.Controls.TextBox> objects.</span></span>  
  
```xaml  
<Window x:Class="SDKSample.Window1"  
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
    Title="Extended Glass in WPF" Height="300" Width="400"   
    Loaded="OnLoaded" Background="Transparent"  
    >  
  <Grid ShowGridLines="True">  
    <DockPanel Name="mainDock">  
      <!-- The border is used to compute the rendered height with margins.  
           topBar contents will be displayed on the extended glass frame.-->  
      <Border Name="topBar" DockPanel.Dock="Top" >  
        <Grid Name="grid">  
          <Grid.ColumnDefinitions>  
            <ColumnDefinition MinWidth="100" Width="*"/>  
            <ColumnDefinition Width="Auto"/>  
          </Grid.ColumnDefinitions>  
          <TextBox Grid.Column="0" MinWidth="100" Margin="0,0,10,5">Path</TextBox>  
          <TextBox Grid.Column="1" MinWidth="75" Margin="0,0,0,5">Search</TextBox>  
        </Grid>  
      </Border>  
      <Grid DockPanel.Dock="Top" >  
        <Grid.ColumnDefinitions>  
          <ColumnDefinition/>  
        </Grid.ColumnDefinitions>  
        <TextBox Grid.Column="0" AcceptsReturn="True"/>  
      </Grid>  
    </DockPanel>  
  </Grid>  
</Window>  
```  
  
 <span data-ttu-id="ec344-124">En la siguiente imagen se muestra el marco de vidrio ampliado en una aplicación [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ec344-124">The following image illustrates the glass frame extended into a [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] application.</span></span>  
  
 <span data-ttu-id="ec344-125">**Marco de vidrio ampliado en una**  [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]**aplicación**.</span><span class="sxs-lookup"><span data-stu-id="ec344-125">**Glass Frame Extended into a**  [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]  **Application.**</span></span>  
  
 <span data-ttu-id="ec344-126">![Marco de vidrio ampliado en una aplicación WPF.](../../../../docs/framework/wpf/graphics-multimedia/media/wpfextendedglassintoclient.PNG "WPFextendedGlassIntoClient")</span><span class="sxs-lookup"><span data-stu-id="ec344-126">![Glass Frame Extended into a WPF application.](../../../../docs/framework/wpf/graphics-multimedia/media/wpfextendedglassintoclient.PNG "WPFextendedGlassIntoClient")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec344-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="ec344-127">See Also</span></span>  
 [<span data-ttu-id="ec344-128">Información general del Administrador de ventanas de escritorio</span><span class="sxs-lookup"><span data-stu-id="ec344-128">Desktop Window Manager Overview</span></span>](/windows/desktop/dwm/dwm-overview)  
 [<span data-ttu-id="ec344-129">Información general de desenfoque del Administrador de ventanas de escritorio</span><span class="sxs-lookup"><span data-stu-id="ec344-129">Desktop Window Manager Blur Overview</span></span>](/windows/desktop/dwm/blur-ovw)  
 <span data-ttu-id="ec344-130">[DwmExtendFrameIntoClientArea](/windows/desktop/api/dwmapi/nf-dwmapi-dwmextendframeintoclientarea) (DwmExtendFrameIntoClientArea [función])</span><span class="sxs-lookup"><span data-stu-id="ec344-130">[DwmExtendFrameIntoClientArea](/windows/desktop/api/dwmapi/nf-dwmapi-dwmextendframeintoclientarea)</span></span>
