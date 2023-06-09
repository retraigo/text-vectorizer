# Vectorizer

- Text vectorizer in TypeScript. Based on scikit-learn's `CountVectorizer` and `TfidfTransformer`.

## Usage

```ts
const data = [
  "twinkle twinkle little star",
  "How I wonder what you are",
  "up above the world so high",
  "like a diamond in the sky",
];

const cv = new CountVectorizer({ lowercase: true });

const vec = cv.fit(data).transform(data);

const tv = new TfIdfTransformer();

const vec2 = tv.fit(vec).transform(vec);

console.log(vec2);
```

<details> 
  <summary>Output</summary>
  <pre>
    <code>
[
  Float32Array(20) [
    3.386294364929199, 2.386294364929199,
    2.386294364929199,                 0,
                    0,                 0,
                    0,                 0,
                    0,                 0,
                    0,                 0,
                    0,                 0,
                    0,                 0,
                    0,                 0,
                    0,                 0
  ],
  Float32Array(20) [
                    0,                 0,
                    0, 2.386294364929199,
    2.386294364929199, 2.386294364929199,
    2.386294364929199, 2.386294364929199,
    2.386294364929199,                 0,
                    0,                 0,
                    0,                 0,
                    0,                 0,
                    0,                 0,
                    0,                 0
  ],
  Float32Array(20) [
                    0,                  0,
                    0,                  0,
                    0,                  0,
                    0,                  0,
                    0,  2.386294364929199,
    2.386294364929199, 1.6931471824645996,
    2.386294364929199,  2.386294364929199,
    2.386294364929199,                  0,
                    0,                  0,
                    0,                  0
  ],
  Float32Array(20) [
                    0,                  0,
                    0,                  0,
                    0,                  0,
                    0,                  0,
                    0,                  0,
                    0, 1.6931471824645996,
                    0,                  0,
                    0,  2.386294364929199,
    2.386294364929199,  2.386294364929199,
    2.386294364929199,  2.386294364929199
  ]
]
    </code>
  </pre>
</details>
