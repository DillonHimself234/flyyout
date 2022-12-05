namespace Flyout;

public static class MauiProgram
{
	public static MauiApp CreateMauiApp()
	{
		var builder = MauiApp.CreateBuilder();
		builder
			.UseMauiApp<App>()
			.ConfigureFonts(fonts =>
			{
				fonts.AddFont("OpenSans-Regular.ttf", "OpenSansRegular");
				fonts.AddFont("OpenSans-Semibold.ttf", "OpenSansSemibold");
			});

		return builder.Build();
	}
}




<?xml version="1.0" encoding="utf-8" ?>
<Shell xmlns="http://schemas.microsoft.com/dotnet/2021/maui"
       xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
       xmlns:controls="clr-namespace:Flyout.Controls"
       xmlns:views="clr-namespace:__XamlGeneratedCode__"
       x:Class="Flyout.AppShell">
    <Shell.FlyoutHeader>
        <Grid>
            <Image Source="header-image.png"/>
        </Grid>
    </Shell.FlyoutHeader>    
        <FlyoutItem Title="Cats"
                Icon="cat.png">
        <Tab>
            <ShellContent ContentTemplate="{DataTemplate views:CatsPage}" />
        </Tab>
    </FlyoutItem>
    <FlyoutItem Title="Dogs"
                Icon="dog.png">
        <Tab>
            <ShellContent ContentTemplate="{DataTemplate views:DogsPage}" />
        </Tab>
    </FlyoutItem>
    <MenuItem Text="Help"
               IconImageSource="help.png"
              Command="{Binding HelpCommand}"
              CommandParameter="https://learn.microsoft.com/dotnet/maui/fundamentals/shell"/>
    <Shell.FlyoutFooter>
        <Grid>
            <Image Source="footer-image.png"/>
        </Grid>
    </Shell.FlyoutFooter>

</Shell>





<?xml version = "1.0" encoding = "UTF-8" ?>
<Application xmlns="http://schemas.microsoft.com/dotnet/2021/maui"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:local="clr-namespace:Flyout"
             x:Class="Flyout.App">
    <Application.Resources>
        <ResourceDictionary>
            <ResourceDictionary.MergedDictionaries>
                <ResourceDictionary Source="Resources/Styles/Colors.xaml" />
                <ResourceDictionary Source="Resources/Styles/Styles.xaml" />
            </ResourceDictionary.MergedDictionaries>
        </ResourceDictionary>
    </Application.Resources>
</Application>

