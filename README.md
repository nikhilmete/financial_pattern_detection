# Financial Market Vision & Quantitative Pattern Detection

A complete Python project that combines **quantitative candlestick pattern detection** with **computer vision** techniques for financial chart analysis.

## Project Overview

This project demonstrates two complementary approaches to pattern detection in financial markets:

1. **Quantitative Pattern Detection**  
   Rule-based detection of classic candlestick patterns (Doji, Hammer, Engulfing, Morning/Evening Star, etc.) directly from OHLCV data.

2. **Financial Market Vision**  
   Computer vision pipeline that analyzes chart images (candlestick charts) using OpenCV — edge detection, contour analysis, and basic shape recognition to support visual pattern identification.

## Project Structure

```
financial_pattern_detection/
├── data/                  # Downloaded market data (CSV)
├── charts/                # Generated chart images
├── models/                # Saved models / detectors (future use)
├── notebooks/
│   └── pattern_detection.ipynb
├── src/
│   ├── __init__.py
│   ├── data_fetcher.py    # Download OHLCV data via yfinance
│   ├── pattern_detector.py# Quantitative candlestick pattern rules
│   ├── vision_analyzer.py # OpenCV-based chart image analysis
│   ├── visualizer.py      # Plotting & highlighting detected patterns
│   └── main.py            # End-to-end pipeline
├── requirements.txt
└── README.md
```

## Quick Start

```bash
# 1. Install dependencies
pip install -r requirements.txt

# 2. Run the full pipeline (example: AAPL, last 6 months)
python -m src.main --ticker AAPL --period 6mo

# 3. Or open the interactive notebook
jupyter notebook notebooks/pattern_detection.ipynb
```

## Key Features

- Fetch real market data (stocks, ETFs, crypto) with `yfinance`
- Detect 10+ classic candlestick patterns quantitatively
- Generate professional candlestick charts
- Apply computer vision (Canny edges, contours, Hough lines) on chart images
- Highlight detected patterns on charts
- Export results and annotated images

## Detected Patterns (Quantitative)

| Pattern              | Type          | Description                              |
|----------------------|---------------|------------------------------------------|
| Doji                 | Reversal      | Open ≈ Close                             |
| Hammer / Hanging Man | Reversal      | Small body, long lower shadow            |
| Inverted Hammer      | Reversal      | Small body, long upper shadow            |
| Bullish Engulfing    | Reversal      | Green candle engulfs previous red        |
| Bearish Engulfing    | Reversal      | Red candle engulfs previous green        |
| Morning Star         | Bullish       | 3-candle bullish reversal                |
| Evening Star         | Bearish       | 3-candle bearish reversal                |
| Three White Soldiers | Continuation  | Three strong green candles               |
| Three Black Crows    | Continuation  | Three strong red candles                 |
| Shooting Star        | Bearish       | Small body, long upper shadow after up   |

## Example Output

```
Detected Patterns for AAPL (last 6 months):
- 2024-08-05: Bullish Engulfing
- 2024-09-12: Hammer
- 2024-10-03: Doji
...
```

## Extending the Project

- Add more patterns (Harami, Piercing Line, Dark Cloud Cover…)
- Train a CNN / YOLO model on labeled chart images for pure vision-based detection
- Integrate real-time data feeds
- Build a simple Streamlit / Gradio dashboard
- Backtest pattern performance

## Requirements

- Python 3.9+
- See `requirements.txt`

## License

Educational / research use. Free to modify and extend.

