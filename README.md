# Construindo-um-App-usando-Sensor-de-Movimento-com-React-Native

[1]: https://www.dio.me/projects/construindo-um-app-usando-sensor-de-movimento-com-react-native ""
[2]: https://github.com/VagnerBellacosa/140_ConstruindoAppSensorMovimentoReactNative ""
[3]: https://github.com/react-native-sensors/react-native-sensors ""

Vamos detalhar o desafio de construir um app de lanterna com React Native que utiliza o sensor de movimento do celular. Vamos dividir o projeto em módulos e fornecer exemplos práticos.

**Módulo 1: Configuração do Ambiente**
Antes de começar, é necessário configurar o ambiente de desenvolvimento para React Native. Isso inclui a instalação do Node.js, Watchman, React Native CLI e Android Studio ou Xcode para emulação.

**Módulo 2: Criação do Projeto**
Utilize o comando `react-native init NomeDoProjeto` para criar um novo projeto React Native. Isso criará a estrutura básica do projeto para você começar a trabalhar.

**Módulo 3: Implementação da Interface**
Desenvolva a interface do usuário (UI) do app de lanterna. Isso pode incluir um botão para ligar e desligar a lanterna e um indicador visual que mostra se a lanterna está ligada ou não.

**Módulo 4: Integração com o Sensor de Movimento**
Para detectar o movimento de chacoalhar, você pode usar a biblioteca `react-native-sensors` que fornece acesso aos sensores do dispositivo¹[3]. Você precisará monitorar os dados do acelerômetro para detectar um padrão de chacoalhada.

**Módulo 5: Controle da Lanterna**
Para controlar a lanterna do dispositivo, você pode usar a API nativa do dispositivo. No Android, isso é feito através do `CameraManager`, enquanto no iOS, você usará o `AVFoundation`.

**Módulo 6: Testes e Depuração**
Teste o app em diferentes dispositivos para garantir que a lanterna acende corretamente ao tocar na tela e ao chacoalhar o celular. Use ferramentas de depuração para resolver quaisquer problemas que surgirem.

**Exemplo Prático:**
```javascript
import { Vibration, TouchableOpacity } from 'react-native';
import Torch from 'react-native-torch';
import RNShake from 'react-native-shake';

class App extends Component {
  componentDidMount() {
    RNShake.addEventListener('ShakeEvent', () => {
      // Liga a lanterna ao chacoalhar o celular
      Torch.switchState(true);
      Vibration.vibrate(500); // Feedback tátil
    });
  }

  componentWillUnmount() {
    RNShake.removeEventListener('ShakeEvent');
  }

  handlePress = () => {
    // Liga ou desliga a lanterna ao tocar na tela
    Torch.switchState(!this.state.isTorchOn);
    this.setState({ isTorchOn: !this.state.isTorchOn });
  };

  render() {
    return (
      <TouchableOpacity onPress={this.handlePress} style={styles.container}>
        {/* UI do App */}
      </TouchableOpacity>
    );
  }
}
```
Este código é um exemplo simplificado. Ele mostra como você pode ligar a lanterna ao chacoalhar o celular e ao tocar na tela. Lembre-se de ajustar o código conforme necessário para o seu projeto específico e realizar testes adequados.

[1]: https://www.youtube.com/watch?v=VDgihqrZUQg ""
[2]: https://www.youtube.com/watch?v=JxAxBGN5QRo ""
[3]: https://www.youtube.com/watch?v=dGZZXQJAwA4 ""
[4]: https://www.dio.me/projects/construindo-um-app-usando-sensor-de-movimento-com-react-native ""
[5]: https://github.com/ablemosjr/reactnative-flashlight ""
[6]: https://github.com/VagnerBellacosa/140_ConstruindoAppSensorMovimentoReactNative ""
[7]: https://github.com/Sgtrona/flashlight-dio ""
[8]: http://bit.ly/fabricadeApps ""
[9]: https://pastebin.com/ ""

O App de lanterna é um projeto interessante que combina a funcionalidade prática de uma lanterna com a detecção de movimento usando React Native. Vou detalhar mais sobre o funcionamento e os recursos desse aplicativo:

**Funcionalidades Principais:**
- **Ligar/Desligar Lanterna:** O usuário pode controlar a lanterna do celular tocando na tela, o que é uma funcionalidade básica de qualquer app de lanterna.
- **Detecção de Movimento:** A característica única deste app é a capacidade de acender a lanterna ao detectar o movimento específico de chacoalhar o celular. Isso é possível através do uso de sensores de movimento disponíveis no dispositivo.

**Tecnologias Utilizadas:**
- **React Native:** Uma framework para desenvolvimento de aplicativos móveis usando JavaScript e React, que permite criar uma experiência de usuário nativa tanto para Android quanto para iOS.
- **Bibliotecas de Sensores:** Para acessar e utilizar os sensores de movimento do dispositivo, são utilizadas bibliotecas como `react-native-sensors`¹[3], que facilitam a integração com o hardware do celular.

**Desenvolvimento do App:**
1. **Criação do Projeto:** Inicia-se com a configuração do ambiente de desenvolvimento e a criação do projeto React Native.
2. **Interface do Usuário:** Desenvolve-se a UI com componentes React Native, como botões e indicadores de status.
3. **Integração com Sensores:** Implementa-se a lógica para detecção de movimento, utilizando o acelerômetro do dispositivo para identificar quando o celular é chacoalhado.
4. **Controle da Lanterna:** Utiliza-se APIs nativas do sistema operacional para ligar e desligar a lanterna do dispositivo.
5. **Testes:** Realiza-se testes em diferentes dispositivos para assegurar que o app funcione corretamente em várias condições e modelos de celular.

**Exemplo de Código:**
```javascript
import { Vibration, TouchableOpacity } from 'react-native';
import Torch from 'react-native-torch';
import RNShake from 'react-native-shake';

class App extends Component {
  // ... restante do código

  componentDidMount() {
    RNShake.addEventListener('ShakeEvent', () => {
      Torch.switchState(true); // Liga a lanterna ao chacoalhar
      Vibration.vibrate(500); // Feedback tátil
    });
  }

  // ... restante do código
}
```
Este trecho de código demonstra como você pode adicionar a funcionalidade de ligar a lanterna ao chacoalhar o celular. É importante notar que este é apenas um exemplo simplificado e que o desenvolvimento completo do app envolverá mais detalhes e funcionalidades.

Para mais informações e tutoriais sobre como criar um app de lanterna com React Native, você pode consultar recursos educacionais e vídeos disponíveis online²[1]³[2]. Esses recursos podem oferecer uma visão mais aprofundada sobre o processo de desenvolvimento e as melhores práticas.

https://drive.google.com/drive/folders/1Kuh5tysH7-UFuSLHX0IQIIh2xcghHUIX?usp=sharing

https://github.com/ismaelsousa/dio-flashlight

https://docs.google.com/presentation/d/1zSHZ8xBvWNUv6ZY21fXr7UseLm5BVeSc/edit?usp=sharing&ouid=105300330738120646134&rtpof=true&sd=true
