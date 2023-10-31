# 🕸 embeddings-radar-chart 🕸

## 🎯 Project Overview

This project explores the visual representation of word embeddings, particularly the BERT embeddings, which consist of 768 dimensions. The challenge was to represent these embeddings in a readable manner without compromising on the number of dimensions displayed.

To achieve this, words were plotted in a radar (or spider) chart, where the goal was to find an order that minimize the correlation between dimensions that are closed to each other, ensuring a clearer representation.

## 🚀 Approach

1. **Problem Complexity**: Recognizing the NP-Complete nature of the problem, akin to the Travelling Salesman Problem, I opted for a genetic algorithm.
2. **Algorithm Strategy**: The genetic algorithm aimed to position each dimension next to its most correlated counterpart and oppose the least correlated ones. However, it reached a plateau after 250 generations.
3. **Dimension Analysis and Treament**: The correlations between the dimensions were low, with the majority of absolute correlation values lying between 0.3 and 0.4. To standardize and provide a uniform scale for these dimensions, each dimension was first centered by subtracting the mean and then scaled by dividing it by the standard deviation. Given that the direction of correlation (positive or negative) could lead to ambiguity in visual interpretation, the analysis solely concentrated on the absolute values of these correlations, ensuring clarity and straightforwardness in subsequent visualizations.
4. **Gaussian Filter Application**: Given the low correlation values, the visualizations didn't appear as expected. The order found made the radar charts slightly less randomized but not fully coherent. To enhance the visualization, a Gaussian filter was applied to smoothen the curve, yielding much clearer results.

## 🧐 Results Interpretation

While there is still much work to be done to refine and fully understand these visual representations, the current results showcase the utility of this tool. The radar charts provide a tangible way to observe the evolution of a word or a sentence and highlight the closeness or disparity between two or more words or sentences. They offer a promising foundation to delve deeper into the nuances of embeddings and to explore fresh perspectives in natural language processing.


## 🎨 Visualization

You can see the outcomes of this approach in the following images and GIFs:
- Proximity and differences between word embeddings
- Evolution of sentence embeddings, word by word

![Many Plots](./imgs/many-plots.png)
![Sentence Complete](./imgs/sentences_complete.png)
![Evolution GIF](./imgs/animation.gif)

## 🔧 Getting Started

The entire project is encapsulated in a notebook. All required dependencies are specified within.

For a smooth experience:
1. Clone the repository.
2. Create a virtual environment (`venv`) to ensure isolation of dependencies.
3. Activate the `venv` and install dependencies.

```bash
git clone <repository_link>
python3 -m venv myenv
source myenv/bin/activate
pip install -r requirements.txt
```

## 💡 Contribution & Feedback

Feel free to fork, raise issues or provide feedback. Your insights could further enhance the visualization and understanding of embeddings!

---

*Designed with ❤️ by [Your Name](Your_GitHub_Profile_Link)*
```

Replace placeholders like `<repository_link>`, `path_to_image1.png`, etc., with the actual links or paths. This markdown can be saved as a `README.md` file in your repository.