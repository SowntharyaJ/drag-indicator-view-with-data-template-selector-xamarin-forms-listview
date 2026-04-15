# How to use drag indicator view with datatemplateselector in Xamarin.Forms ListView

This example demonstrate how to use drag indicator view with datatemplateselector in Xamarin.Forms ListView.

## Sample

```xaml
<ContentPage.Resources>
    <ResourceDictionary>
        <local:MyDataTemplateSelector x:Key="MessageTemplateSelector">
            <local:MyDataTemplateSelector.IncomingDataTemplate>
                <DataTemplate>
                    <Grid ColumnSpacing="2" Padding="0">
                        <Grid.ColumnDefinitions>
                            <ColumnDefinition Width="*"/>
                            <ColumnDefinition Width="40"/>
                        </Grid.ColumnDefinitions>
                        <Grid.RowDefinitions>
                            <RowDefinition Height="*"/>
                            <RowDefinition Height="20"/>
                        </Grid.RowDefinitions>
                        <Frame OutlineColor="Transparent" HasShadow="False" BackgroundColor="#03A9F4">
                            <StackLayout Orientation="Horizontal">
                                <sync:DragIndicatorView ListView="{x:Reference listView}" HorizontalOptions="Center" VerticalOptions="Start">
                                    <Grid Padding="5">
                                        <Image Source="dragcircle.png" HeightRequest="40" WidthRequest="30"/>
                                    </Grid>
                                </sync:DragIndicatorView>
                                <Label TextColor="White" Text="{Binding Text}" LineBreakMode="WordWrap" VerticalOptions="Center"/>
                            </StackLayout>
                        </Frame>
                        <Label FontSize="Micro" Grid.Row="1" Text="{Binding MessagDateTime, StringFormat='{0:MM/dd/yyyy hh:mm tt}'}" TextColor="Gray" LineBreakMode="NoWrap"/>
                    </Grid>
                </DataTemplate>
            </local:MyDataTemplateSelector.IncomingDataTemplate>
            <local:MyDataTemplateSelector.OutgoingDataTemplate>
                <DataTemplate>
                    <Grid ColumnSpacing="2" Padding="0">
                        <Grid.ColumnDefinitions>
                            <ColumnDefinition Width="40"/>
                            <ColumnDefinition Width="*"/>
                        </Grid.ColumnDefinitions>
                        <Grid.RowDefinitions>
                            <RowDefinition Height="*"/>
                            <RowDefinition Height="20"/>
                        </Grid.RowDefinitions>
                        <Frame Grid.Row="0" OutlineColor="Transparent" HasShadow="False" Grid.Column="1" BackgroundColor="#FFFFFF">
                            <StackLayout Orientation="Horizontal">
                                <Label TextColor="Black" HorizontalTextAlignment="Start" Text="{Binding Text}" LineBreakMode="WordWrap" />
                                <sync:DragIndicatorView ListView="{x:Reference listView}" HorizontalOptions="EndAndExpand" VerticalOptions="EndAndExpand">
                                    <Grid Padding="3">
                                        <Image Source="dragsquare.png" HeightRequest="30" WidthRequest="30"/>
                                    </Grid>
                                </sync:DragIndicatorView>
                            </StackLayout>
                        </Frame>
                        <Label Grid.Row="1" FontSize="Micro" Grid.Column="1" HorizontalTextAlignment="End"  Text="{Binding MessagDateTime, StringFormat='{0:MM/dd/yyyy hh:mm tt}'}" TextColor="Gray" LineBreakMode="NoWrap"/>
                    </Grid>
                </DataTemplate>
            </local:MyDataTemplateSelector.OutgoingDataTemplate>
        </local:MyDataTemplateSelector>
    </ResourceDictionary>
</ContentPage.Resources>

    <sync:SfListView x:Name="listView" 
                    ItemTemplate="{StaticResource MessageTemplateSelector}" 
                    ItemsSource="{Binding Messages}"
                    ItemSize="105"
                    SelectionMode="None"
                    BackgroundColor="#FFFAF0"
                    DragStartMode="OnDragIndicator"/>
```

**[View document in Syncfusion Xamarin Knowledge base](https://www.syncfusion.com/kb/12492/how-to-use-drag-indicator-view-with-datatemplateselector-in-xamarin-forms-listview)**

## Requirements to run the demo

* [Visual Studio 2017](https://visualstudio.microsoft.com/downloads/) or [Visual Studio for Mac](https://visualstudio.microsoft.com/vs/mac/)
* Xamarin add-ons for Visual Studio (available via the Visual Studio installer).

## Troubleshooting

### Path too long exception

If you are facing path too long exception when building this example project, close Visual Studio and rename the repository to short and build the project.
