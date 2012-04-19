WPF FlashMessage
================

This is custom control that provides a way to alert users whether an operation was successfully completed or not.
Why use MessageBox when you have the powerfull WPF in your hands?

The Motivation
--------------

Aren't you tired of all the MessageBoxes on your applications? Isn't there a better way to alert users whether an
operation was successfully completed? For years I used MessageBox or a static label in WinForms applications,
and they came with me when I started to migrate to WPF.

However, WPF is so much more powerfull than that, and I thought why not create something different?
Because let's face it, using MessageBox is like using javascript alert function in a web page, don't you think?.
So it is settle, we need something new, but what? Well, once I was a [Rails] (http://rubyonrails.org/) developer
and Rails has a interesting [flash message system]
(http://guides.rubyonrails.org/action_controller_overview.html#the-flash),
so I thought of creating a control that acts slightly similar.

How does it work?
-----------------

So, let's see how the control works. It has two mainly properties: MessageType and Message.

`MessageType` whether a Error, Success or Notice. These influence which style the control uses.

`Message` it's the message itself. As soon as this property is changed, the FlashMessage fades in automatically.

`FadesOutAutomatically` besides clicking on the close button, you can configure whether it fades out automatically.

`FadeOutTime` it specifies how much time the FlashMessage waits to fades out after it fades in;

A Glimpse
-----------------

![Glimpse](http://i1.code.msdn.s-msft.com/new-control-to-get-rid-of-377ffb5a/image/file/56088/2/sem%20t%c3%adtulo.png)

Usage
-----------------

Add a reference of `FlashMessage.dll` to your project.

Add the namespace to your Window:

    xmlns:flash="clr-namespace:FlashMessage;assembly=FlashMessage"

Add the control wherever you like:

    <Grid>
        <Grid.ColumnDefinitions>
            <ColumnDefinition Width="*"/>
        </Grid.ColumnDefinitions>
        <Grid.RowDefinitions>
            <RowDefinition Height="Auto"/>
            <RowDefinition Height="27"/>
        </Grid.RowDefinitions>

        <flash:FlashMessage Grid.Row="0" Grid.Column="0" Message="Successfully saved." MessageType="Success"/>

        <!--Others controls-->
    </Grid>