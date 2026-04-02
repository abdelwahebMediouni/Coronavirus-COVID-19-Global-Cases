Pattern pattern = Pattern.compile("<StsCd>(.*?)</StsCd>");
Matcher matcher = pattern.matcher(xml);

StringBuffer result = new StringBuffer();

while (matcher.find()) {
    String value = matcher.group(1);

    String replacement =
        "<Sts><Prtry>" + value + "</Prtry></Sts>";

    matcher.appendReplacement(result, replacement);
}

matcher.appendTail(result);

xml = result.toString();
