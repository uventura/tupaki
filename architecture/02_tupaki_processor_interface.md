# Tupaki Processor Interface

To achieve a good modularization, the processor will have a fixed
interface, then the artifact will not depend of the tupaki simulator.

The interface will be:
```cpp
    tupaki::BaseProcessor
    {
        virtual long long int getReg(std::string register_id);
	virtual long long int setReg(std::string register_id, long long int value);

    	virtual void instructionCaller(std::string instruction_name, ...);
	virtual std::string getInstructionHexCode(std::string instruction);
    }
    
```

This should be extended over the time, but should be a simplified interface.
