# Automata Crypto Trading Framework

**Introduction**

Presenting an innovative yet straightforward cryptocurrency trading framework, developed using the capabilities of Aider AI with GPT-4 Turbo technology. A significant portion, over 50%, of this framework's code is generated by [Aider AI](https://github.com/paul-gauthier/aider), a sophisticated coding assistant, under the direction of an experienced developer. This project demonstrates the exceptional potential of AI in coding, showcasing its effective contribution to complex software development processes.

## **Key Features**

### **AI-Enhanced Codebase**
- Utilizing GPT-4 Turbo with a 128k context, Aider AI plays a crucial role in creating more than half of the framework's code.
- This method speeds up the development process and ensures high code quality and efficiency, demonstrating AI's practical application in contemporary software engineering.

### **Simplicity and Structure**
- Despite its technical depth, the framework maintains an uncomplicated and well-organized structure.
- It incorporates the ccxt.pro API for direct connectivity to various cryptocurrency exchanges, providing access to real-time market data.
- ZeroMQ is employed for effective inter-process communication (IPC), enabling smooth interactions between the framework's components.

### **Central Sequencing Design**
- The architecture is centered around a central sequencing design, essential for delineating components.
- This approach simplifies development and maintenance and is crucial for structured algorithmic logic in trading strategy execution.

### **Asynchronous Programming**
- Designed as an asyncio application, notable for its non-blocking and concurrent operation capabilities.
- This is particularly advantageous in trading, where handling multiple tasks simultaneously and responding quickly to market changes are essential.
- The asyncio structure enhances the framework's performance in trading operation execution.

### **Simple Trading Strategy**
- Features a basic trading strategy that places orders at the top of the book or mid-price, based on configuration, every 10 seconds.
- This strategy focuses on optimizing buy or sell prices for potentially more profitable trades.

**Conclusion**

This cryptocurrency trading framework is more than just an efficient trading tool; it is a testament to the collaboration between advanced AI coding technology and expert human oversight. It represents AI's transformative impact in software development, especially relevant in the ever-evolving field of cryptocurrency trading.

## Prerequisites

Before setting up the trading system, ensure that you have Miniconda and PM2 installed on your system.

## Initial Setup

1. Create a directory for inter-process communication (IPC):
   ```
   mkdir -p /tmp/sequencer
   ```

2. Set up your environment variables for the API key and secret used by the cryptocurrency exchange. Export them in your shell:
   ```
   export CDC_API_KEY=your_api_key
   export CDC_SECRET=your_secret
   ```
   Replace `your_api_key` and `your_secret` with your actual API key and secret values.

3. Configure the `conf/opti_trade_config.ini` file with the desired strategy parameters:
   ```
   [OptiTrade]
   exchange = cryptocom
   symbol = CRO/USD
   tick_size = 0.00001
   order_quantity = 1
   sleep_time_sec = 10
   client_order_id_prefix = OPTI-
   order_side = buy
   exec_mode = TOB
   ```
   Adjust the parameters as needed for your trading strategy.

## Running the System

To run the trading system, use PM2, a process manager for Node.js applications with a built-in load balancer. The `automata.config.js` file in the repository is configured to start the various components of the system.

Start the system using the following command:
   ```
   pm2 start automata.config.js
   ```

You can monitor the processes with:
   ```
   pm2 list
   ```

To stop the system, use:
   ```
   pm2 stop automata.config.js
   ```

## Contributing

Contributions are welcome! If you have a suggestion that would improve this, please fork the repository and create a pull request. You can also simply open an issue with the tag "enhancement".
Don't forget to give the project a star! Thanks again!

## License

This project is licensed under the MIT License - see the LICENSE file for details.
