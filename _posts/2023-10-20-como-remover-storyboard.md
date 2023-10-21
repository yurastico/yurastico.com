---
layout: post
title: Como remover o arquivo Main Storyboard
tags: UIKit IOS Programação  
cover: post-5-1
---

### Esse aqui é um guia super rápido para eu mesmo de como remover o arquivo Main.storyboard de uma aplicação UIKit no Xcode 14/15 para trabalhar apenas com ViewCode, então vamos lá. 

### 1- Remover o arquivo Main.storyboard, obviamente:

<figure class="screenshot-banner-box">
    <img style="" src="/assets/img/post-5-2.jpg" alt="Captura de tela ilustrando passo a passo"/>
</figure>


### 2- clicar no arquivo info.plist e apagar o tag de "Storyboard main" (clicando no -)

<figure class="screenshot-banner-box">
    <img style="" src="/assets/img/post-5-3.jpg" alt="Captura de tela ilustrando passo a passo"/>
</figure>


### 3- clicar em "Project" -> Build Settings -> no filtro escrever "Main", e então apagar a chave da Tag "UIKit Main Storyboard File Base Name" 

<figure class="screenshot-banner-box">
    <img style="" src="/assets/img/post-5-4.jpg" alt="Captura de tela ilustrando passo a passo"/>
</figure>

### 4- agora em SceneDelegate precisamos adicionar o seguinte trecho de código:

```swift
      guard let scene = (scene as? UIWindowScene) else { return }
        let window = UIWindow(windowScene: scene)
        window.rootViewController = ViewController()
        window.makeKeyAndVisible()
        self.window = window
```

<figure class="screenshot-banner-box">
    <img style="" src="/assets/img/post-5-5.jpg" alt="Captura de tela ilustrando passo a passo"/>
</figure>



### 5- E então, para garantir que funcinou vamos mudar o background na View controller: 

``` swift
 override func viewDidLoad() {
        super.viewDidLoad()
        // Do any additional setup after loading the view.
        view.backgroundColor = .blue
    }
```

<figure class="screenshot-banner-box">
    <img style="" src="/assets/img/post-5-6.jpg" alt="Captura de tela ilustrando passo a passo"/>
</figure>

É isto, como mencionei no inicio esse tutorial é que eu vivo esquecendo como faz isso, mas se ajudar alguém já está ótimo :) 


