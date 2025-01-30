# Run DeepSeek R1 Locally with Ollama and Python

![DeepSeek logo](https://media2.dev.to/dynamic/image/width=1000,height=420,fit=cover,gravity=auto,format=auto/https%3A%2F%2Fdev-to-uploads.s3.amazonaws.com%2Fuploads%2Farticles%2Febnqqeyhlp15i12yvohy.jpg)


## Introduction
In recent years, artificial intelligence and machine learning have revolutionized how we approach complex problems across various domains, from natural language processing to computer vision. In this context, tools like [DeepSeek R1](https://github.com/deepseek-ai/DeepSeek-R1/blob/main/DeepSeek_R1.pdf) have stood out for their ability to deliver efficient and high-performance solutions to challenging tasks that other models struggle with.

![DeepSeek R1 Comparison](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/wxfp8w3j9e0224o0d71n.png)

## What is DeepSeek R1?
**DeepSeek R1** is an artificial intelligence platform designed to simplify the implementation of deep learning models in real-world applications. It offers a variety of features, such as real-time data processing, custom model training, and efficiency—all wrapped in open-source code.

---

## DeepSeek Locally and Ollama
There are many ways to use DeepSeek, one of which is through an [API Key](https://api-docs.deepseek.com/). However, here we will focus on running it locally using [Ollama](https://ollama.com/) and Python.

**First, what is Ollama?** Simply put, Ollama is a tool that makes it easy to use advanced artificial intelligence models, such as those that generate text or answer questions, without requiring complex technical knowledge. It allows anyone to run and interact with these models easily, whether on a personal computer or in the cloud, making AI technology more accessible for everyday tasks or creative projects.

To install Ollama, you need to visit this website: [https://ollama.com/download](https://ollama.com/download), select your operating system, run the installer, and complete the setup. If everything is set up correctly, execute `ollama help` in your terminal, and you should see this:


```
Large language model runner

Usage:
  ollama [flags]
  ollama [command]

Available Commands:
  serve       Start ollama
  create      Create a model from a Modelfile
  show        Show information for a model
  run         Run a model
  stop        Stop a running model
  pull        Pull a model from a registry
  push        Push a model to a registry
  list        List models
  ps          List running models
  cp          Copy a model
  rm          Remove a model
  help        Help about any command

Flags:
  -h, --help      help for ollama
  -v, --version   Show version information

Use "ollama [command] --help" for more information about a command.

```


The next step is to **download the model**. On the Ollama website's search page [https://ollama.com/search](https://ollama.com/search), you can find many models to use.

In this post, we will use **DeepSeek R1 models** [https://ollama.com/library/deepseek-r1](https://ollama.com/library/deepseek-r1):


```
DeepSeek-R1-Distill-Qwen-1.5B
ollama run deepseek-r1:1.5b

DeepSeek-R1-Distill-Qwen-7B
ollama run deepseek-r1:7b

DeepSeek-R1-Distill-Llama-8B
ollama run deepseek-r1:8b

DeepSeek-R1-Distill-Qwen-14B
ollama run deepseek-r1:14b

DeepSeek-R1-Distill-Qwen-32B
ollama run deepseek-r1:32b

DeepSeek-R1-Distill-Llama-70B
ollama run deepseek-r1:70b
```


Each model differs in terms of its parameters. Essentially, the parameters of an AI model are like "internal settings" that it adjusts to learn from data and make predictions. The more parameters a model has, the more complex and capable it can be, but it also requires more processing power.

**Note:** Computational power is very important when choosing a model. The higher the number of parameters, the more computational power your machine will need.

After downloading the model, your chat will show this:

```
>>> Send a message (/? for help)
```

Now you have a local AI on your computer.

---

## Ollama and Python 🐍
To connect Python and Ollama with DeepSeek, first, you need to create your Python file and install the Ollama package using this command:

```
pip install ollama
```

I created the following code as an example:

```
import ollama

model = "deepseek-r1:7b"

while True:
    Myprompt = input("You: ")
    answer = ollama.generate(model=model, prompt=Myprompt)
    print("DeepSeek:", answer["response"])
```

1. Import the package using `import ollama`.
2. Define your model using `model = "deepseek-r1:7b"`.
3. Start a loop with `while True:`.
4. Capture user input using `prompt = input("You: ")`.
5. Generate a response from the model using  `answer = ollama.generate(model=model, prompt=prompt)`.
6. Print the response using `print("DeepSeek:", answer["response"])`.

## Conclusion
DeepSeek R1, combined with Ollama, offers a powerful yet accessible way to run advanced AI models locally on your machine. This setup allows you to experiment with AI technology without the need for extensive infrastructure or cloud resources.

By following the steps outlined in this article, you can easily install Ollama, download DeepSeek R1 models, and integrate them with Python for seamless interaction. This approach not only simplifies the deployment process but also opens up opportunities for customization and experimentation in your AI projects.

---
Thanks for reading 🙃



- Follow my dev.to account: [@mattsu014](https://dev.to/mattsu014)

- Original Post: [Run DeepSeek R1 Locally with Ollama and Python](https://dev.to/mattsu014/run-deepseek-r1-locally-with-ollama-and-python-44b6)



