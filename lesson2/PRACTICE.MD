### **Понимание компонентов и JSX**

#### **Практическое задание:**

1.  **Создать функциональный компонент, который отображает текст.**
2.  **Добавить компонент с props (например, приветственное сообщение с именем пользователя).**

----------

#### **Шаги:**

1.  **Настройка проекта:**
    
    -   Если проект ещё не создан, выполните команды:
        
        ```bash
        npx expo-cli init MyFirstApp
        cd MyFirstApp
        npm start
        
        ```
        
    -   Откройте проект в редакторе кода (например, Visual Studio Code).
2.  **Создание простого компонента, отображающего текст:**
    
    -   В файле `App.js` измените код на следующий:
        
        ```jsx
        import React from 'react';
        import { Text, View } from 'react-native';
        
        const App = () => {
          return (
            <View>
              <Text>Привет, React Native!</Text>
            </View>
          );
        };
        
        export default App;
        
        ```
        
3.  **Добавление компонента с props:**
    
    -   Создайте новый компонент `Greeting`:
        
        ```jsx
        const Greeting = (props) => {
          return <Text>Привет, {props.name}!</Text>;
        };
        
        ```
        
    -   Используйте этот компонент в `App`:
        
        ```jsx
        const App = () => {
          return (
            <View>
              <Greeting name="Алексей" />
              <Greeting name="Мария" />
            </View>
          );
        };
        
        ```
        
    -   Теперь на экране отображаются приветствия для двух пользователей.
4.  **Запустите проект:**
    
    -   Откройте приложение на эмуляторе, в симуляторе или на реальном устройстве через **Expo Go**.

----------

### **Стилизация компонентов**

#### **Практическое задание:**

1.  **Создать экран с приветствием и кнопкой.**
2.  **Стилизация текста (цвет, шрифт, выравнивание).**
3.  **Добавить кнопку с обработчиком события.**

----------

#### **Шаги:**

1.  **Обновление компонента App:**
    
    -   Измените код в файле `App.js` на следующий:
        
        ```jsx
        import React, { useState } from 'react';
        import { Text, View, Button, StyleSheet } from 'react-native';
        
        const App = () => {
          const [message, setMessage] = useState('Привет, React Native!');
        
          const changeMessage = () => {
            setMessage('Вы нажали на кнопку!');
          };
        
          return (
            <View style={styles.container}>
              <Text style={styles.text}>{message}</Text>
              <Button title="Нажми меня" onPress={changeMessage} />
            </View>
          );
        };
        
        const styles = StyleSheet.create({
          container: {
            flex: 1,
            justifyContent: 'center',
            alignItems: 'center',
            backgroundColor: '#f0f0f0',
          },
          text: {
            color: 'blue',
            fontSize: 20,
            marginBottom: 20,
          },
        });
        
        export default App;
        
        ```
        
2.  **Разбор кода:**
    
    -   **Состояние (`useState`):**
        -   `message` хранит текущий текст сообщения.
        -   Функция `setMessage` обновляет значение `message`.
    -   **Обработчик события:**
        -   `changeMessage` вызывается при нажатии кнопки и изменяет сообщение.
    -   **Стилизация:**
        -   Стили созданы с помощью `StyleSheet.create` и применены через атрибут `style`.
3.  **Проверка работы:**
    
    -   Запустите проект через **npm start**.
    -   Нажмите кнопку и убедитесь, что текст изменяется.
