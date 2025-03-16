# Skincare Chat Assistant: Limitations & Future Improvements

## Current Limitations

The current implementation of the Skincare Chat Assistant cannot handle certain types of queries effectively:

1. **How to use the product** - The system currently lacks specific handling for usage instructions of products
2. **FAQs about products** - Common questions about products are not specifically addressed
3. **Hair concerns** - The current system focuses on skincare and does not address hair-related issues

These limitations exist because they were not included in the original project scope. To implement these features, additional columns from the product dataset would be needed, and the query understanding node would need to be enhanced to subclassify product queries into different types (usage instructions, recommendations, etc.).

## Potential Improvements

### Performance Enhancements
* **Caching mechanism** - Implementing a response cache can significantly improve response times for common queries
* **Batch processing** - System could be enhanced to handle multiple queries together for improved throughput
* **Asynchronous programming** - Independent tasks could be executed in parallel to reduce overall response time

### User Experience
* **Enhanced UI** - A more polished user interface would make the system more attractive and easier to use (not implemented as this is a demo project)
* **Personalization** - Further refinement of user preference tracking for more customized recommendations

## Current Functionalities

### Data Processing
* Embedded all required information of each product as a single chunk for improved retrieval
* Experimented with open-source embedding models; OpenAI embeddings performed best for this application

### Search Capabilities
* Implemented Tavily for web searches as it outperformed other Web Search APIs (including SerpAPI)
* Results are filtered based on trusted skincare information sources

### Query Understanding
* Developed a sophisticated query understanding node with extensive prompting
* System classifies user intent and routes queries accordingly
* Extracts important information like user preferences automatically

### Product Recommendations
* Retrieved results from product vector database are filtered based on user preferences
* Products are reranked based on how many user skin concerns they address
* Provides relevant product attributes to help users make informed decisions

### Conversation Handling
* System handles casual conversations and greetings naturally
* Manages off-topic discussions while gently guiding conversation back to skincare topics
* Maintains context throughout the conversation for a more coherent experience

### Memory/History
* The chatbot contains the history of the past queries
* Uses the context of the past queries to answer the present queries
* Stores important user preferences so that they can be incorported whenever required